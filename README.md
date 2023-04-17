# kubectl

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&amp;logoColor=white)](https://github.com/rolehippie/kubectl)
[![General Workflow](https://github.com/rolehippie/kubectl/actions/workflows/general.yml/badge.svg)](https://github.com/rolehippie/kubectl/actions/workflows/general.yml)
[![Readme Workflow](https://github.com/rolehippie/kubectl/actions/workflows/readme.yml/badge.svg)](https://github.com/rolehippie/kubectl/actions/workflows/readme.yml)
[![Galaxy Workflow](https://github.com/rolehippie/kubectl/actions/workflows/galaxy.yml/badge.svg)](https://github.com/rolehippie/kubectl/actions/workflows/galaxy.yml)
[![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/kubectl)](https://github.com/rolehippie/kubectl/blob/master/LICENSE)
[![Ansible Role](https://img.shields.io/badge/role-rolehippie.kubectl-blue)](https://galaxy.ansible.com/rolehippie/kubectl)

Ansible role to install and configure the Kubernetes CLI.

## Sponsor

Building and improving this Ansible role have been sponsored by my current and previous employers like **[Cloudpunks GmbH](https://cloudpunks.de)** and **[Proact Deutschland GmbH](https://www.proact.eu)**.

## Table of content

- [Requirements](#requirements)
- [Default Variables](#default-variables)
  - [kubectl_checksum](#kubectl_checksum)
  - [kubectl_ctx_checksum](#kubectl_ctx_checksum)
  - [kubectl_ctx_download](#kubectl_ctx_download)
  - [kubectl_ctx_install](#kubectl_ctx_install)
  - [kubectl_ctx_version](#kubectl_ctx_version)
  - [kubectl_download](#kubectl_download)
  - [kubectl_extra_configs](#kubectl_extra_configs)
  - [kubectl_fixed_version](#kubectl_fixed_version)
  - [kubectl_from_repository](#kubectl_from_repository)
  - [kubectl_general_configs](#kubectl_general_configs)
  - [kubectl_keyring](#kubectl_keyring)
  - [kubectl_ns_checksum](#kubectl_ns_checksum)
  - [kubectl_ns_download](#kubectl_ns_download)
  - [kubectl_ns_install](#kubectl_ns_install)
  - [kubectl_ns_version](#kubectl_ns_version)
  - [kubectl_version](#kubectl_version)
- [Discovered Tags](#discovered-tags)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Requirements

- Minimum Ansible version: `2.10`


## Default Variables

### kubectl_checksum

Checksum for the kubectl release

#### Default value

```YAML
kubectl_checksum: sha256:a076f5eff0710de94d1eb77bee458ea43b8f4d9572bbb3a3aec1edf0dde0a3e7
```

### kubectl_ctx_checksum

Checksum for the kubectl ctx plugin release

#### Default value

```YAML
kubectl_ctx_checksum: sha256:e887e4e2b3dd4c94d0ecdb84270fb4fac2e65c4d5b0ee461e688fb8089fd4900
```

### kubectl_ctx_download

Download URL for the kubectl ctx plugin release

#### Default value

```YAML
kubectl_ctx_download: https://github.com/ahmetb/kubectx/releases/download/v{{ kubectl_ctx_version
  }}/kubectx
```

### kubectl_ctx_install

Install the kubectl ctx plugin

#### Default value

```YAML
kubectl_ctx_install: true
```

### kubectl_ctx_version

Version of the kubectl ctx plugin release to install

#### Default value

```YAML
kubectl_ctx_version: 0.9.3
```

### kubectl_download

Download URL for the kubectl release

#### Default value

```YAML
kubectl_download: http://storage.googleapis.com/kubernetes-release/release/v{{ kubectl_version
  }}/bin/linux/amd64/kubectl
```

### kubectl_extra_configs

List of extra configs

#### Default value

```YAML
kubectl_extra_configs: []
```

#### Example usage

```YAML
kubectl_extra_configs:
  - name: global
    path: /etc/kubernetes/config
    owner: root
    group: root
    mode: u=rwX,g=rX,o=rX
    current: foobar
    clusters:
      - name: foobar
        ca:  ...
        server: https://10.13.37.1:6443
    users:
      - name: admin
        cert: ...
        key: ...
    contexts:
      - name: foobar
        cluster: foobar
        user: admin
```

### kubectl_fixed_version

Pin version if installed from repository

#### Default value

```YAML
kubectl_fixed_version: false
```

### kubectl_from_repository

#### Default value

```YAML
kubectl_from_repository: false
```

### kubectl_general_configs

List of general configs

#### Default value

```YAML
kubectl_general_configs: []
```

#### Example usage

```YAML
kubectl_general_configs:
  - name: global
    path: /etc/kubernetes/config
    owner: root
    group: root
    mode: u=rwX,g=rX,o=rX
    current: foobar
    clusters:
      - name: foobar
        ca:  ...
        server: https://10.13.37.1:6443
    users:
      - name: admin
        cert: ...
        key: ...
    contexts:
      - name: foobar
        cluster: foobar
        user: admin
```

### kubectl_keyring

Path for the repository keyring

#### Default value

```YAML
kubectl_keyring: /usr/share/keyrings/kubernetes-archive-keyring.gpg
```

### kubectl_ns_checksum

Checksum for the kubectl ns plugin release

#### Default value

```YAML
kubectl_ns_checksum: sha256:509c97c0882e688ae8fad8aa13524cc7c003e4883db447a905bdb47d64c13bdc
```

### kubectl_ns_download

Download URL for the kubectl ns plugin release

#### Default value

```YAML
kubectl_ns_download: https://github.com/ahmetb/kubectx/releases/download/v{{ kubectl_ns_version
  }}/kubens
```

### kubectl_ns_install

Install the kubectl ns plugin

#### Default value

```YAML
kubectl_ns_install: true
```

### kubectl_ns_version

Version of the kubectl ns plugin release to install

#### Default value

```YAML
kubectl_ns_version: 0.9.3
```

### kubectl_version

Version of the kubectl release to install

#### Default value

```YAML
kubectl_version: 1.18.8
```

## Discovered Tags

**_kubectl_**


## Dependencies

- None

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
