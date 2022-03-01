# bridget-riley
 
## project workflow (ERJ 3/1/2022)
1. set up quire project directory locally with git
2. push git quire project to github
3. integrate with like netlify, (Add new Site->Import an Existing project) obtail netlify domain like `elaxed-kirch-7c2f51.netlify.app`
4. choose CNAME, like `bridget-riley.publications.britishart.yale.edu`
5. make a certificate signing request
    1. like `openssl req -out briley.csr -new -newkey rsa:2048 -keyout briley.key`
    2. submit csr to `https://systemeu.globalsign.com/bm/public/certificate/poporder.do?domain=PAR096758117786p9r60a515v82n`
    3. recieve crt from csr submission
    4. obtain intermediate crt from `https://support.globalsign.com/ca-certificates/intermediate-certificates/organizationssl-intermediate-certificates`
6.  Use Yale ITS service now (IP and DNS Support) to set up CNAME https://yale.service-now.com/it
    1. origin = `elaxed-kirch-7c2f51.netlify.app`
    2. domain name = `bridget-riley.publications.britishart.yale.edu`
8. set up Amazon Cloud Front distribution with origin and alternate domain name
    1.  Choose Import in Amazon Certificate Manager, upload crt, private key, and certificate chain
    2.  set up new distribution with https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/CNAMEs.htmls
    3. set up redirect https://stackoverflow.com/questions/42325344/how-to-force-cloudfront-to-use-https-redirect-http-https
