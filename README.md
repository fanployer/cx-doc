# Webhook Documentation: Communicating Candidate Information

## Endpoint
```
POST https://cx.fanployer.com/webhook/{job_id}/candidate?api-key={your_api_key}
```

## Headers
- `Content-Type`: `application/json`

## Parameters
### Body Parameters (JSON)
- `email` (string): The applicant's email address.
- `name` (string): The applicant's name.
- `status` (enum): The applicant's status. Possible values:
  - `new`: New applicant.
  - `interview-scheduled`: Applicant invited for an interview.
  - `rejected`: Applicant rejected.
  - `hired`: Applicant hired.

## Sample Request
```json
POST https://cx.fanployer.com/webhook/12345/candidate?api-key=your_api_key
Headers:
{
  "Content-Type": "application/json"
}

Body:
{
  "email": "example@domain.com",
  "name": "John Doe",
  "status": "new"
}
```

## Response
### Successful Response
```json
{
  "message": "Applicant successfully received"
}
```

### Error Response
```json
{
  "error": "Invalid request or authentication failed"
}
```

## Security Through HTTPS

Using HTTPS ensures that communication between your ATS and our server is encrypted. This means that data transmitted, such as the email addresses and names of applicants, is secure during transit. HTTPS offers encryption, integrity, and authentication, making it difficult for third parties to intercept or alter the data and ensuring communication with the correct server.

### Mandatory Use of HTTPS

HTTPS is mandatory for this webhook to ensure the security of the transmitted data. By enforcing HTTPS, we ensure that your data remains safe and protected during communication. Make sure your API key remains confidential and is only shared with authorized individuals and systems.
