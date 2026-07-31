# cs10_stig — Ansible role (cs10-stig)

**Ansible hardening role** for **CentOS Stream 10** (DISA STIG). Suitable for playbooks, Packer/Ansible provisioners, and golden-image pipelines. Search keywords: `ansible`, `ansible-role`, `centos`, `centos-stream`, `compliance`, `cs10`, `devsecops`, `disa`, `disa-stig`, `hardening`, `infrastructure`, `openscap`, `rhel`, `security`.

StigForge-exported Ansible role **`cs10_stig`** · release **`0.2.4`**.
Matrix cell status: **`green`**.

## Install (Ansible Galaxy)

This repository root **is** the Ansible role (Galaxy-style layout). OpenSCAP evidence
lives under `compliance/` and is not loaded when the role runs.

From **Ansible Galaxy** (after import; namespace `stigready`):

```bash
ansible-galaxy role install stigready.cs10_stig,0.2.4
```

From **GitHub** (public):

```yaml
# requirements.yml
roles:
  - src: https://github.com/stigready/cs10-stig
    scm: git
    version: v0.2.4   # or an immutable commit SHA
    name: cs10_stig
```

```bash
ansible-galaxy role install -r requirements.yml -p ./roles
ansible-playbook -i inventory site.yml   # role: cs10_stig
```

## Verification status (this release)

Evidence was produced by **docker verify + OpenSCAP** on the factory CI run cited below.

| Profile | Score | Floor | Gate | Ansible | Evidence tested (UTC) |
|---|---:|---:|---|---|---|
| `stig` | **95.71%** ✓ | 90.0% | PASS ✓ | rc 0 | 20260731T085542Z |

Full artifacts per profile: `compliance/releases/0.2.4/<profile>/` (`score.json`, `results.xml`, `report.html`, `evidence.json`, `evidence-report.html`, `poam.md`).

## Reports & review

- **[REVIEW.md](REVIEW.md)** — linked evidence index for product owner review
- **[reports/index.html](reports/index.html)** — HTML report index
- **[CHANGELOG.md](CHANGELOG.md)** — release notes and verify summary

## Verify the score (customer)

Re-run OpenSCAP in Docker and compare to this release's evidence:

```bash
make prove RELEASE=0.2.4
```

Or score your own `results.xml`: see **[compliance/README.md](compliance/README.md)**.

## License

- **[LICENSE](LICENSE)** (MIT) — StigForge export packaging
- **[NOTICE](NOTICE)** — ComplianceAsCode / BSD-3-Clause task body attribution

## Factory

- Monorepo: [stigready/stigforge](https://github.com/stigready/stigforge) @ `5c2fc8f5ad23bdd66e77fe95e1363d5a10c9f05d`
- CI run: https://github.com/stigready/stigforge/actions/runs/30617333526
- Catalog: [https://stigready.com/#stigforge](https://stigready.com/#stigforge)

