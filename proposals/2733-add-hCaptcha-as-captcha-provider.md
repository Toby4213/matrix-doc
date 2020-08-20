# MSC02733 : Add hCaptcha as captcha provider

This MSC proposes to generalize the use of a captcha api in the matrix spec and that 
hCaptch is to be added to to provide a more privacy focused alternative to reCaptcha.

## Context

Since google is well known for their misuse of their customers data and general disregard 
for basic privacy rights it is desireable to distance the Matrix spec from such a company.
The ubiquitously used reCaptcha is one such mechanism to accumulate more private data for Google.

## Proposal

The Matrix spec should not directly reference reCaptcha as the only captcha provider. 
The spec should be generalized to use multiple captcha API's. hCaptcha should be added first
as a captcha provider and also should be used as the default moving forward.

This move would have multiple benefits:
* Not relying on Google
* Protecting users privacy, see [here](https://www.hcaptcha.com/privacy)
* The captchas are easier to solve and aren't confusing like reCaptcha sometimes can be (only from my own and anecdotal experiences)
* Used by Cloudflare, see [here](https://blog.cloudflare.com/moving-from-recaptcha-to-hcaptcha/).
* Supports [Privacy Pass](https://privacypass.github.io/)

## Alternatives

Some alternatives have been discussed in multiple Issues [1](https://github.com/vector-im/element-web/issues/3606) [2](https://github.com/matrix-org/matrix-doc/issues/1281).
There are generally two views regarding alternatives for reCaptcha. Design oriented and Security/Privacy oriented.
For Design, there are two notable mentions:
* [VisualCaptcha](https://visualcaptcha.net/)
* [MTCaptcha](https://www.mtcaptcha.com/)
Regarding security and privacy the by far best option is [hCaptcha](https://www.hcaptcha.com/):

## Security considerations

Arguably hCaptch isn't as bot proof as reCaptcha is, but to what degree is uncertain.