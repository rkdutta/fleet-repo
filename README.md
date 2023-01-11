# fleet-repo

```
├── README.md
├── clusters
│   └── ota
│       ├── flux-system
│       └── tenant-t1-kustomization.yaml (pointing to tenants/overlays/tenant-t1)
└── tenants
    ├── base (base folder can be further modularized into env specific)
    │   ├── git-repository.yaml
    │   ├── helm-repository.yaml
    │   ├── kustomization.yaml
    │   ├── networkpolicy.yaml
    │   ├── permission.yaml
    │   └── tenant-sync.yaml
    └── overlays
        └── tenant-t1
            ├── kustomization.yaml (points to dev,tst)
            ├── dev
            │   ├── kustomization.yaml (inherits base & apply patches for tenant)
            │   ├── namespaces.yaml
            │   └── tenant-patch.yaml
            └── tst
                ├── kustomization.yaml (inherits base & apply patches for tenant)
                ├── namespaces.yaml
                └── tenant-patch.yaml
```