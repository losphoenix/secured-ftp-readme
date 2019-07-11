# Usage Doc

- For `ibc` only, use `alt` + left click `connection` to launch hidden logon page.
  Specify username `ibc` and password. Please use `ibc` for username now.

- Use the account `ibc` to login

- In the page `Files`, check the top-right corner, click the `New Company` button to create a new client. Besides, the company'd receive an email asking him/her to click an link provided by Amazon Cognito to activate his/her account.

![new-company.png](asset/new-company.png)

- Every time `ibc` created a new company account, `secure-share` will create
  - A dedicated S3 folder for this company

- When a company account logged in `secure-share`, he/she needs to generate a  RSA key pair in the `Credentials` page. This key pair is used to encrypt files when `ibc` want to share files with the company

![generate-credential.png](asset/generate-credential.png)

- User can import RSA key pairs in `Credential` page. To make it, users need to be sure the desired RSA key pairs are already in his/her computer.

## How to reset a company user

Say the username for this company user is `abc`,

- **In IBC's computer**
  1. Remove the following directories:
    - `${HOME}/secure-share/meta/abc`
    - `${HOME}/secure-share/data/abc`
  2. Remove the following files:
    - `${HOME}/secure-share/meta/ibc/ibc-abc-public.txt`
    - `${HOME}/secure-share/meta/ibc/ibc-abc-private.txt`
  3. Open S3 console, delete folder `abc` in your bucket
  4. Open Cognito console, delete user `abc`
- **In client's computer**, just remove the whole folder `${HOME}/secure-share`
