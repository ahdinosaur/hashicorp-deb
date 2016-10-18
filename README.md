# hashicorp-deb

Debian packages (`.deb` files) for the [Hashicorp ecosystem](https://releases.hashicorp.com):

- [ ] [`vagrant`](https://www.vagrantup.com): there's already `.deb` files [here](https://releases.hashicorp.com/vagrant/)
- [x] [`packer`](https://www.packer.io/)
- [x] [`terraform`](https://www.terraform.io)
- [x] [`vault`](https://www.vaultproject.io)
- [ ] [`consul`](https://www.consul.io)
- [ ] [`nomad`](https://www.nomadproject.io/)
- [ ] [`serf`](https://www.serf.io/)

## scripts

configuration of package versions is stored in `./vars`

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
