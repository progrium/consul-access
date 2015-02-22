# consul-access

Lightweight password protection to Consul HTTP using Nginx.

## Using consul-access

Simply link against a running Consul container using the alias `consul` and provide a username and password with the `HTPASSWD` environment variable:

	$ docker pull progrium/consul-access
	$ docker run -d \
		--link consul:consul \
		--env "HTPASSWD=<username> <password>" \
		--publish 80:80
		progrium/consul-access

## Security

Since HTTP [Basic authentication](https://en.wikipedia.org/wiki/Basic_access_authentication) is used, you should only access this behind SSL otherwise your password is transmitted unencrypted.

## License

BSD
