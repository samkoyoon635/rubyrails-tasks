---
languages:
- ruby
page_type: sample
products:
- azure
- azure-app-service
description: "This is a sample application that you can use to follow along with the Build a Ruby on Rails and MySQL web app in Azure tutorial."
---

# Ruby on Rails sample for Azure App Service

This is a sample application that you can use to follow along with the tutorial at 
[Build a Ruby on Rails and MySQL web app in Azure](https://docs.microsoft.com/azure/app-service/containers/tutorial-ruby-mysql-app). 

This sample application is generated from the default Rails project and modified minimally to make it work with Azure App Service. 

## Quick Start
Follow the commands below.

### DB start
[Local Postgres](https://dataschool.com/learn-sql/how-to-start-a-postgresql-server-on-mac-os-x/)
```bash
# Start up postgres server locally on port 5432
pg_ctl -D /usr/local/var/postgres start

# (Optional) In case of version conflict on brew
brew postgresql-upgrade-database

# Connect to server
psql postgres

# Stop
pg_ctl -D /usr/local/var/postgres stop

# DB create and migrate
rake db:create
rake db:migrate
```
Docker Postgres (Only works as [docker-compose](https://medium.com/better-programming/setting-up-rails-with-postgres-using-docker-426c853e8590))
```bash
# Docker
docker run -d --rm --name my_postgres -e POSTGRES_PASSWORD=881224 -p 5432:5432 postgres:11

# Connect to server
docker exec -it my_postgres psql -U postgres

# define password for user (e.g. postgres)
\password postgres

# DB create and migrate
rake db:create
rake db:migrate
```
### Server start
```bash
# Install bundler(v1.16.2, 1.13.6)
gem install bundler:1.16.2

# Install required packages
bundle install --path vendor/bundle

```


## License

See [LICENSE](https://github.com/Azure-Samples/rubyrails-tasks/blob/master/LICENSE.md).

## Contributing

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.
