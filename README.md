<div id="top-header" style="with:100%;height:auto;text-align:right;">
    <img src="./resources/docs/images/pr-banner-long.png">
</div>

# INFRASTRUCTURE PLATFORM POSTGRE 18.2

[![Generic badge](https://img.shields.io/badge/version-1.0-blue.svg)](https://shields.io/)
[![Open Source? Yes!](https://badgen.net/badge/Open%20Source%20%3F/Yes%21/blue?icon=github)](./)
[![MIT license](https://img.shields.io/badge/License-MIT-blue.svg)](./LICENSE)

This Infrastructure Platform repository is designed for back-end projects and provides separate platforms:

- **Core Database Platform:** Linux Alpine version 3.23 + Postgres 18.2

The goal of this repository is to offer developers a consistent framework for local development, mirroring real-world deployment scenarios. In production, the API may be deployed on an AWS EC2 / GCP GCE or instance or distributed across Kubernetes pods, while the database would reside on an AWS RDS instance. thus, network connection between platforms are decoupled.

Platform engineering is the discipline of creating and managing an internal developer platform (IDP) to provide developers with self-service tools, automated workflows, and standardized environments. By reducing cognitive load and complexity, it allows software engineering teams to innovate faster and more efficiently, building on the principles of DevOps. The IDP acts like a product, where developers are customers, and aims to streamline the entire software development lifecycle, from building and testing to deploying and monitoring.

### Key principles and goals

- Self-service: Provide developers with easy-to-use tools and automated workflows to manage their own infrastructure needs without having to file tickets or rely on other teams.
- Standardization: Use standardized tools and environments to ensure consistency, reliability, and security across projects.
- Reduced cognitive load: Abstract away underlying complexity so developers can focus on writing code and delivering business value rather than managing infrastructure details.
- Developer experience: Build a positive and productive environment for developers, making them feel empowered and less frustrated.
- Operational efficiency: Automate repetitive tasks and standardize processes to improve the speed and reliability of software delivery.

### How it works

- Internal Developer Platform (IDP): A dedicated platform built by the platform engineering team that provides a curated set of tools, services, and infrastructure.
- Golden Paths: Predefined, optimized workflows and best practices that developers can follow to accomplish common tasks quickly and easily.
- Treating the platform as a product: Platform engineers treat their IDP like a product, with developers as their customers, to ensure it meets the needs of the organization.

### Documentation:

- [What is platform engineering? - IBM](https://www.ibm.com/think/topics/platform-engineering)
- [Understanding platform engineering - Red Hat](https://www.redhat.com/en/topics/platform-engineering)
- [Platform engineering - Prescriptive Guidance - AWS](https://docs.aws.amazon.com/prescriptive-guidance/latest/aws-caf-platform-perspective/platform-eng.html)
- [What is an internal developer platform (IDP)? - Google Cloud](https://cloud.google.com/solutions/platform-engineering)
- [What is platform engineering? - Microsoft](https://learn.microsoft.com/en-us/platform-engineering/what-is-platform-engineering)
- [What is Platform engineering? - Github](https://github.com/resources/articles/what-is-platform-engineering)
<br><br>

## <a id="platform-usage"></a>Use this Platform Repository for your own REST API repositories

Repository directories structure overview:
```bash
.
├── apirest         # Core directory binded in Docker main container for back-end
│   └── ...         # sub-module or detach with the real project respository
│
├── platform
│   │
│   └── pgsql-18.2
│      ├── Makefile
│      └── docker
│          ├── Dockerfile
│          ├── README.md
│          ├── docker-compose-w-data.yml
│          ├── docker-compose.network.yml
│          ├── docker-compose.yml
│          ├── docker-ensure-initdb.sh
│          └── docker-entrypoint.sh
│
├── resources
│   │
│   ├── automation
│   │   ├── local
│   │   │   └── Makefile
│   │   └── remote
│   │       └── ...
│   ├── databases
│   │   ├── pgsql-backup.sql
│   │   └── pgsql-init.sql
│   └── docs
│       └── images
│           ├── pr-banner-long.png
│           └── ...
│
├── .env          # Platforms main values applied
├── .env.example  # Platforms main values example
├── Makefile      # Automated commands into recipes
└── README.md
```
<br>

Set up platform:

- Copy `.env.example` to `.env` to adjust platforms settings
- The database container can start with `DATABASE_CAAS_MEM=128M` *(CAAS = Container As A Service)*

### Estimated consumption

This is the overview of the estimated host machine consumption:
- *Your local values could be slightly different*
- *(?) Your custom project abbreviation*
```
$ sudo docker stats

CONTAINER ID   NAME           CPU %   MEM USAGE / LIMIT    MEM %   NET I/O         BLOCK I/O         PIDS
4afa058af7a9   (?)-pgsql-dev  0.04%   21.23MiB  / 128MiB   16.59%  1.17kB / 126B   1.47MB / 59.5MB   6
```
<br>

## Contributing

Contributions are very welcome! Please open issues or submit PRs for improvements, new features, or bug fixes.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/YourFeature`)
3. Commit your changes (`git commit -am 'feat: Add new feature'`)
4. Push to the branch (`git push origin feature/YourFeature`)
5. Create a new Pull Request
<br><br>

## License

This project is open-sourced under the [MIT license](LICENSE).

<!-- FOOTER -->
<br>

---

<br>

- [GO TOP ⮙](#top-header)

<div style="with:100%;height:auto;text-align:right;">
    <img src="./resources/docs/images/pr-banner-long.png">
</div>