---
title: Personalizar Codespaces para tu cuenta
intro: '{% data variables.product.prodname_codespaces %} utiliza tu repositorio de `dotfiles` en {% data variables.product.product_name %} para personalizar cualquier codespace nuevo que crees.'
product: '{% data reusables.gated-features.codespaces %}'
permissions: 'Cualquiera puede crear un repositorio `dotfiles` para personalizar {% data variables.product.prodname_codespaces %} para su cuenta de usuario.'
redirect_from:
  - /github/developing-online-with-github-codespaces/personalizing-github-codespaces-for-your-account
versions:
  free-pro-team: '*'
---

{% data reusables.codespaces.release-stage %}

Los Dotfiles son archivos y carpetas de sistemas parecidos a Unix que comienzan con `.` y que controlan la configuración de aplicaciones y shells de tu sistema. Puedes alamacenar y administrar tus dotfiles en un repositorio en {% data variables.product.prodname_dotcom %}. Para encontrar consejos y tutoriales sobre qué incluir en tu repositorio de `dotfiles`, consulta la sección [GitHub maneja dotfiles](https://dotfiles.github.io/).

Si tu cuenta de usuario en {% data variables.product.prodname_dotcom %} es propietaria de un repositorio público llamado `dotfiles`, {% data variables.product.prodname_dotcom %} utilizará este repositorio automáticamente para personalizar el ambiente de tu codespace. Actualmente, no son compatibles los repositorios `dotfiles` privados.

Tu repositorio `dotfiles` puede incluir los alias de tu shell y tus preferencias, cualquier herramienta que quieras instalar, o cualquier otra personalización del codespace que quieras hacer.

La personalización de codespaces utilizando el repositorio `dotfiles` aplica a cualquier codespace que crees. Los mantenendores de proyecto también pueden definir una configuración predeterminada que aplique a cada codespace para un repositorio que cree alguien más. {% data reusables.codespaces.codespace-config-order %} Para obtener más información, consulta la sección "[Configurar {% data variables.product.prodname_codespaces %} para tu proyecto](/github/developing-online-with-codespaces/configuring-codespaces-for-your-project)".

Cuando creas un codespace nuevo, {% data variables.product.prodname_dotcom %} clona tu repositorio `dotfiles` hacia el ambiente del codespace, y busca uno de los siguientes archivos para configurar el ambiente.

* _install.sh_
* _install_
* _bootstrap.sh_
* _bootstrap_
* _setup.sh_
* _setup_

Si no encuentra alguno de estos archivos, entonces cualquier archivo o carpeta en `dotfiles` que comience con `.` se enlazará simbólicamente al directorio `~` o `$HOME` del codespace.

Cualquier cambio a tu repositorio `dotfiles` se aplicará únicamente a cada codespace nuevo, y no afectará a ningún codespace existente.

Para obtener más información, consulta la sección "[Personalizing](https://docs.microsoft.com/en-us/visualstudio/online/reference/personalizing) en la documentación de {% data variables.product.prodname_vscode %}.

{% note %}

**Nota:** Actualmente, {% data variables.product.prodname_codespaces %} no es compatible con la personalización de la configuración de _Usuario_ para el editor de {% data variables.product.prodname_vscode %} con tu repositorio de `dotfiles`. Puedes configurar ajustes predeterminados de _Workspace_ y _Remote [Codespaces]_ para un proyecto específico en el repositorio de éste. Para obtener más información, consulta la sección "[Configurar {% data variables.product.prodname_codespaces %} para tu proyecto](/github/developing-online-with-codespaces/configuring-codespaces-for-your-project#creating-a-custom-codespace-configuration)".

{% endnote %}


### Leer más

* "[Crear un repositorio nuevo](/github/creating-cloning-and-archiving-repositories/creating-a-new-repository)".
