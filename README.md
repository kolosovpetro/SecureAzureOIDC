# Secure OIDC implementation using Azure AD and ASP .NET Framework

In this manuscript we discuss the problem of secure storage and transfer of access tokens between microservices.
Web browser may store access tokens both, in local storage or in cookie files.
We propose a secure implementation to store and transfer auth cookies between microservices
using Azure Active Directory, OpenID Connect and ASP .NET Web Framework.

## Build and run in Intellij IDEA

- Install `MikTeX`: https://miktex.org/download
- Update `MikTeX`
- Install `SumatraPDF` viewer: https://www.sumatrapdfreader.org/download-free-pdf-viewer
- Install `Intellij IDEA Ultimate`: https://www.jetbrains.com/idea/download/#section=windows
- Activate `Intellij IDEA Ultimate`
- Install `TeXiFy IDEA` plugin: https://plugins.jetbrains.com/plugin/9473-texify-idea
- Clone this repository locally: `https://github.com/kolosovpetro/github-latex-template.git`
- Open `github-latex-template` folder in `Intellij IDEA Ultimate` and configure as follows
    - LaTeX Configuration
      ![LaTeX Configuration](img/latex_configuration.PNG?raw=true "LaTeX Configuration")
    - BibTeX Configuration
      ![BibTeX Configuration](img/bibtex_configuration.PNG?raw=true "BibTeX Configuration")
- Configure Inverse Search in `Intellij IDEA` for SumatraPDF: `Tools -> LaTeX -> Configure Inverse Search`
- Compile document using `Shift + F10`

## Configure CI / CD

Set repository secrets

- `GH_ACCESS_TOKEN`: Generate GitHub Personal access token at
  `Settings -> Developer Settings -> Personal access tokens -> Generate mew token`

## Actions and their trigger policy

- `build-pdf.yml` builds project using `TeXLive`. Triggered on `pull_request`, `push` to `develop` branch
- `build-and-deploy-pdf.yml` builds project using `TeXLive` and deploys to `GitHub Pages`. Triggered on `push` to `main`
  branch