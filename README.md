# vagrant-postgres-14
A vagrant box (CentOS 7) to install Postgres 14

## How to use

	# Clone it locally:
    $ git clone git@github.com:bin9wei/vagrant-postgres-14.git vagrant-postgres-14

    # cd to directory:
    $ cd vagrant-postgres-14

    # Bring up virtual box
    $ vagrant up

    # ssh to virtual box
    $ vagrant ssh

    # Shut down virtual box
    $ vagrant halt

## What does it do

It creates a centOS 7 virtual box with Postgres 14 installed. 

Once it has started up it will print out how to access the database on the virtual machine. It will look something like this:

```
    default: Successfully created PostgreSQL dev virtual machine.
    default: Your PostgreSQL database has been setup and can be accessed on your local machine on the forwarded port (default: 15432)
    default:   Host: localhost
    default:   Port: 15432
    default:   Database: myapp
    default:   Username: myapp
    default:   Password: dbpass
    default:
    default: Admin access to postgres user via VM:
    default:   vagrant ssh
    default:   sudo su - postgres
    default:
    default: psql access to app database user via VM:
    default:   vagrant ssh
    default:   sudo su - postgres
    default:   PGUSER=myapp PGPASSWORD=dbpass psql -h localhost myapp
    default:
    default: Env variable for application development:
    default:   DATABASE_URL=postgresql://myapp:dbpass@localhost:15432/myapp
    default:
    default: Local command to access the database via psql:
    default:   PGUSER=myapp PGPASSWORD=dbpass psql -h localhost -p 15432 myapp
```

## DB credentials

In `provision.sh`, change if need

```
APP_DB_USER=myapp
APP_DB_PASS=dbpass
```