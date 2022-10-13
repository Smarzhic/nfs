# Role Name

Install NFS

## Требования

Debian или Ubuntu

## Переменные

```yaml
nfs_foldes_create: true
nfs_foldes:
  - path: "/nfs/foo"
    address: "192.168.1.0/24"
    permissions: "(rw,sync,no_subtree_check)"
```

## Пример Playbook

```yaml
- hosts:
    - all

  vars:
    nfs_foldes_create: true
    nfs_foldes:
      - path: "/nfs/foo"
        address: "192.168.1.0/24"
        permissions: "(rw,sync,no_subtree_check)"


  roles:
    - role: nfs
      become: true
```

### Порты для работы NFS

[SecuringNFS](https://wiki.debian.org/SecuringNFS)

```
 ACCEPT          fw      loc             udp     111
 ACCEPT          fw      loc             tcp     111
 ACCEPT          fw      loc             tcp     2049
 ACCEPT          fw      loc             udp     2049
 ACCEPT          fw      loc             tcp     32764:32769
 ACCEPT          fw      loc             udp     32764:32769
```
