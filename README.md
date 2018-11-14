blog
====

This is a deployment of [ghost](https://ghost.org/) and
[ghost-backup](https://github.com/rija/ghost-backup) via
[docker](https://www.docker.com/) and
[docker-compose](https://docs.docker.com/compose/).

## Configuration

The following environment variables are *required*:

| Name                | Purpose                                        |
|---------------------|------------------------------------------------|
| `HOST`              | Hostname and port where `ghost` is accessible. |
| `LETSENCRYPT_EMAIL` | Your email for use with Let's Encrypt.         |

### Mail

You can use [Mailgun](https://mailgun.com) or
[SES](https://aws.amazon.com/ses/) to enable some features of Ghost like
password resets, user invitations, subscribers, and system notifications with
the following environment variables:

| Name             | Purpose                           |
|------------------|-----------------------------------|
| `MAIL_SVC`       | `Mailgun` *or* `SES`              |
| `MAIL_USER`      | Your mail service `username`      |
| `MAIL_PASS`      | Your mail service `password`      |

## Usage

```bash
docker-compose up -d
```

### Backup

```bash
docker exec blog_ghost-backup_1 backup
```

### Restore

```bash
docker exec -it blog_ghost-backup_1 restore -i
```
