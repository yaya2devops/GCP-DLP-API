## Redact Assets w/ Data Loss Prevention API 


- Enable the DLP API from GCP 
- Install the DLP API

```sh
git clone https://github.com/googleapis/nodejs-dlp.git
```

- Install Nodejs and samples 
```sh
cd nodejs-dlp/samples
npm install @google-cloud/dlp
npm install yargs
npm install mime
```


### Inspect Sensitive information
Using `ìnspectString.js` explicit your data.

- E.g. your email address in assets
```sh
node inspectString.js $GCLOUD_PROJECT "My email address is dev@yahya-abulhaj.dev."
```
- E.g. your phone number(s) in assets
```sh
node inspectString.js $GCLOUD_PROJECT "My phone number is +99999999."
```

### Redact sensitive data from images

- Give input to the system e.g. upload the below asset

![Hi From GCP Code Editor](assets-for-real.png)


- from `nodejs-dlp/samples` redact the email address values from the image

```sh
node redactImage.js $GCLOUD_PROJECT ~/assets-for-real.png "" EMAIL_ADDRESS ~/yaya-redacted.png
```

We specified EMAIL_ADDRESS as the infotype to redact. 

In the image, you should notice that the email address is no longer visible.

![This is cool!](yaya-redacted.png)

<h2 align="center">
 
 [Real-time Censoring](assets/poc/hm-hmm.png)
 
</h2>
 
