# dashboard-kubernetes
Expose dashboard kubernetes using Cert-Manager, Nginx Controller and Oauth2 proxy

At this point, we have a dashboard kubernetes and nginx controller already deployed. We wanted to expose the dashboard and expose it to the users (internal team) and every team/user will have a dedicated view.
# Structure
1. **Cert-Manager** will manage the certificates on the dashboard service. 
2. **External-dns** will create an entry on the dedictated hosted zone on the route53 for the service (eg dashboard.ironlab.dev)
3. **Oauth-proxy** will create an oauth2-proxy toward github for the authentication
4. **Users** we have two services accounts admin and basic users: which it will be using for authorization (based on the rbac configuration on the service accounts)
5. **Auth:** two types of configuration for authentication using a basic authentication like  htpasswd or oauth2-proxy
