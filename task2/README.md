# 1. Where would you deploy the frontend app to? Explain
### Option one [not recommended]
Deploy as a container on Kubernetes along with backend. Create a Dockerfile with Nginx as a base. Copy all frontend files along with custom nginx configuration to handle  the request. From ingress point frontend domain to the service create for frontend pods/deployment.
- yaml files in `fe` directory [Dockerfile not included]

### Option two [recommended]
Deploy frontend with CDN providers.
Some of them include 
- [Cloudflare (Cloudflare Pages)](https://pages.cloudflare.com/)
- [AWS S3 with Cloudfront in front](https://aws.amazon.com/premiumsupport/knowledge-center/cloudfront-serve-static-website/)
- [Netlify]()
- ....

There are many providers in this space. Provider can be selected based on cost, performance, availability and may other

Advantages of using this option:
- They provide CDN by default which makes page or static content load much faster where by enhancing user experience.
- Will create much less maintenance.
- Will not have to worry about traffic and scaling of frontend.
- In most cases there is no need for custom automation to be created fro deployment. Platform of choice handles the building and deploying of application based on git activity.

# 2
yaml files in `be` directory

# Notes 
- Here it assumed that Nginx Ingress Controller(ingress-nginx) is already deployed and running with class nginx [https://kubernetes.github.io/ingress-nginx/]
- Assumed namespace to be default for both frontend and backend
- Assumed that images are built and pushed to private docker repository
- Assumed that for both backend and frontend the certificate for domain has been already generated or bought. 
- Certificate request and renewal can be automated using cert-manager, which gets certs from Let's Encrypt