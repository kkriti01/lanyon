---
layout: post
---

# **Read and Parse email attachments**
![](../assets/1.jpg?raw=true)
IMAP and POP3 are mostly used internet mail protocol to fetch email from remote server. 
But we are going to use IMAP here, imaplib implements clients which can be used to communicate with IMAP servers.

Modules that we are going to use
```python
import imaplib
import email
import os
import shutil
import tempfile
from docx import Document
```
email module is used to read email messages, it can also be used to write and send messages. 
We will use tempfile to create temporary directory to download attachment and shutil to remove directory after being used.
We will use docx module which will be used to parse word document.We can install docx module by:

```python
pip install python-docx
```

Credentials to login
```python
LOGIN_EMAIL = ""
LOGIN_PWD = ""
SMTP_SERVER = "imap.gmail.com"
SMTP_PORT = 993
FROM_EMAIL = ''
```

We need to specify credentials for login into email and you can specify sender whose mail you want to read. 
We can also do query by 'FROM', 'TO'.

Login to IMAP server and select folder from which we have to read
```python
m = imaplib.IMAP4_SSL(SMTP_SERVER, SMTP_PORT)
m.login(LOGIN_EMAIL, LOGIN_PWD)
```

select inbox or can specify folder or all
```python
m.select('"inbox"')
```
Login to server using email and password, imaplib implements client which can connect to IMAP4 server.
We can specify folder i.e 'inbox' or any folder from which we want to read the mail.

Search using query like 'FROM' 'TO'
```python
result, data = m.uid('search', None, '(FROM "{}")'.format(FROM_EMAIL))  # search all email and return uids
```
The data that we got here is a list of Ids and we can use these id to fetch subject, body and attachment from the mail.

Fetch data for ids we got in previous step and read attachment and download it into a temporary directory.
```python
for num in data[0].split():
    # Fetch mail from server
    result, data = m.uid('fetch', num, '(RFC822)')
    if result == 'OK':
        raw_email = data[0][1]
        raw_email_string = raw_email.decode('utf-8')
        email_message = email.message_from_string(raw_email_string)

        # Get attachment and parse
        for data in email_message.walk():
            if data.get_content_maintype() == 'multipart':
                continue
            if data.get('Content-Disposition') is None:
                continue
            fileName = data.get_filename()

            # Create a temporary directory to download attachment
            path = tempfile.mkdtemp()
            if bool(fileName):
                filePath = os.path.join(path, fileName)
                if not os.path.isfile(filePath):
                    fp = open(filePath, 'wb')
                    fp.write(data.get_payload(decode=True))
                    fp.close()

                # Use docx module to parse word documents
                document = Document(filePath)
                recruit_data = parse_attachment(document)               
            # Delete temp directory
            shutil.rmtree(path)
```  
After login we can search mail using query like 'FROM', 'TO'. We can pass 'ALL' to fetch all the messages.
For id which we got in previous step, we will fetch mail using 'RFC822' which is internet mail access protocol.
Message that we get here will be binary encode so decode it using .decode('utf-8'). 
After converting data to string we will use 'email' module and will create dictionary of messages using function 
.message_from_string(raw_email_string). Now we will iterate over message using .walk which is used to iterate over
message tree and will check if message contain multipart data or plain text data.If .get_content_maintype() is 'multipart' 
then email contains attachment.We will create a temporary directory using tempfile.mkdtemp() and will download attachment 
in this directory. After parsing from document file will remove this directory using shutil.rmtree(path).  
 
Create document by passing filePath
```python
document = Document(filePath)
recruit_data = parse_attachment(document)
```
Create document from docx module by passing our document file path.
Those document can be used to parse table and paragraph in the documents.

Parse attached documents
```python
def parse_attachment(document):
    paragraphs = []
    data = {}
    for table in document.tables:
        for row in table.rows:
            for cell in row.cells:
                paragraphs.append(cell.text)
    for item in paragraphs:
        if 'Project name' in item:
            data['project_name'] = get_key_value(item)
        if 'Number of positions requested' in item:
            data['no_of_position'] = get_key_value(item)
        if 'Task acronym' in item:
            data['task_acronym'] = get_key_value(item)
        if 'Basic Qualifications' in item:
            data['basic_qualification'] = get_key_value(item)
        if 'Preferred Qualifications' in item:
            data['preferred_qualification'] = get_key_value(item)
        if 'Description of Work' in item:
            data['work_description'] = get_key_value(item)

    return data


def get_key_value(item):
    data = item.split(":")

    if data and len(data) == 2:
        return data
    else:
        return None
 ```       
document that we got in previous step can be used to get tables .The document.tables will give you all
tables in the document. We can iterate over row and cells of table and get text from cells or paragraph. This article is also available on medium [here](https://medium.com/@kriti_shrivastwa/read-and-parse-email-attachment-32d5621178f3)      
