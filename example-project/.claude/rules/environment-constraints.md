# Rule: environment constraints

Hard limits of the target environment. Do not propose solutions that violate these.

- **No admin rights** on end-user machines. Anything requiring elevation is out.
- **Office is Click-to-Run** (Microsoft 365); the add-in deploys via **ClickOnce**.
  Do not assume MSI Office or per-machine installs.
- **Python tooling targets the pinned interpreter** in `tools/.python-version`. Do
  not assume a different runtime.
