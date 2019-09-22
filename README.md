# CLOUDFLARE UPDATE DNS

## Intro

This is a docker image for update cloudflare dns records

## Environment

### Required

* CFKEY="a34a6b6fbc5188acddf94ae93871371f27e9cf"
	* cloudflare API key
* CFUSER="user@example.com"
	* cloudflare auth user email
* CFZONE="example.com"
	* zone name in cloudflare
* CFHOST="host1.example.com host2.example.com"
	* dns records (hosts) for updating IP address, split with space

> The Cloudflare `Global API Key` needs to be used and not the `Origin CA Key`

### Optional

* CFINTERVAL=300
	* interval for updating in seconds, default: 300 seconds

## Examples

```console
docker run -d \
  -e CFKEY=89d0703637ce648749520ff3bc245b8ee2c1a \
  -e CFUSER=juan.enciso@gmail.com \
  -e CFZONE=enciso.site \
  -e CFHOST=ansible-az.enciso.site \
  --restart=always \
  --name=cloudflare-update-dns \
  jenciso/cloudflare-update-dns 
```
