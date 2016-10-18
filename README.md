# hashicorp-deb

helper scripts to build Debian packages (`.deb` files) for the [Hashicorp ecosystem](https://releases.hashicorp.com):

- [ ] [`vagrant`](https://www.vagrantup.com): there's already `.deb` files [here](https://releases.hashicorp.com/vagrant/)
- [x] [`packer`](https://www.packer.io/): [`ahdinosaur/debian-packer`](https://github.com/ahdinosaur/debian-packer)
- [x] [`terraform`](https://www.terraform.io): [`ahdinosaur/debian-terraform`](https://github.com/ahdinosaur/debian-terraform)
- [x] [`vault`](https://www.vaultproject.io): [`ahdinosaur/debian-vault`](https://github.com/ahdinosaur/debian-vault)
- [x] [`consul`](https://www.consul.io): [`ahdinosaur/debian-consul`](https://github.com/ahdinosaur/debian-consul)
- [x] [`nomad`](https://www.nomadproject.io/): [`ahdinosaur/debian-nomad`](https://github.com/ahdinosaur/debian-nomad)
- [x] [`serf`](https://www.serf.io/): [`ahdinosaur/debian-serf`](https://github.com/ahdinosaur/debian-serf)

## scripts

common configuration is shared in `./context`

### `key`

- imports [Hashicorp's gpg key on Keybase](https://keybase.io/hashicorp)

### `download`

in `.downloads`:

- downloads pre-built binaries from [`releases.hashicorp.com`](https://releases.hashicorp.com) using `curl`
- downloads checksum file
- downloads signature of checksum file
- verifies checksum file using signature
- verifies pre-built binary using checksum file

### `build`

in `.builds`:

- creates a debian package directory

### `package`

in `.packages`:

- uses `dpkg-deb` to create `.deb` file

### `install`

- uses `dpkg` to install `.deb` files

## dependencies

- `curl`
- `jq`
- `dpkg`
