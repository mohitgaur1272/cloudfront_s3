# cloudfront_s3
this is for s3 deployment with githubaction
## first of all you have to create ssl certificate with aws service ```ACM``` then you have to create certificate for your domain.
## you can create with the main domain like  ```example.com``` and with the ```*.example.com``` 

### after creating it will give you a ```CNAME``` record so you have to attach in your hostad zone that you have in route53 service.
## After that you have to crate bucket for each envirnment with the specific name with block all public access. your all bucker will be private for security.bca we will use cloudfront for cache and secure our bucket data.
```
dev-march
test-march
prod-march
```
### so now create distribution ```choose origin``` then click on origin access controle settings and create your ```OAC and select```  then select ```redirect http to https``` then click on ```do not enable security protection``` and type ```your domain or subdomain``` in the alternative domian name this is ```mandatory``` then choose ```ssl certificate from the ACM``` if you have subdomain so use *.example.com and if you use single domain so use only example.com then type ```index.html``` in the dafault root section. 

### after that you will get a ```policy for s3 bucket``` so copy and paste in your s3 bucket permission. this is require for that your bucket will access only from cloudfront not a publicly.

#### then after deploying your distirbution you will recive a DNS of cloudfront and access.

#### after that you have to create A record with the alias and select your cloudfront distribution and create rule.



