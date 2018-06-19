---
title: Crear tokens de entorno y variables | Documentos de Microsoft"
description: Actualizar el archivo de enlace para utilizar los tokens de entorno y crear variables en VSTS para automatizar la implementación de aplicaciones de BizTalk Server
ms.custom: ''
ms.date: 11/08/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.prod: biztalk-server
ms.topic: article
ms.assetid: 28bb2d4a-f45c-466d-ba65-0ca8cad0bffd
caps.latest.revision: 4
author: tordgladnordahl
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d84fa393410e3084c87e762140530a45b0b78b5
ms.sourcegitcommit: a0165ec2f1e8b58545638666b7bfa2bf440036fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/09/2017
ms.locfileid: "24054572"
---
# <a name="configure-environmental-tokens-and-variables-for-automatic-deployment"></a>Configurar los tokens de entorno y variables para la implementación automática
Usar variables de Visual Studio Team Services (VSTS) en su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] archivos de enlace.

## <a name="overview"></a>Información general
En un entorno de VSTS, puede agregar las variables y establecerlos en un valor. Por ejemplo, puede crear un *sendPortPath* variable y establezca su valor en una carpeta física en su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]. 

En el [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] archivo de enlace de la aplicación, las variables configurables pueden ser cualquier elemento dentro de una etiqueta XML, como el nombre de la ubicación de recepción, host, URI del puerto de envío y así sucesivamente. 

Estas variables son específicas de su entorno de VSTS y puede utilizarse para implementar la misma aplicación para varios [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] entornos. 

Le mostramos cómo agregar la variable VSTS en el archivo de enlace y cómo crear la variable dentro de VSTS. 

## <a name="add-variables-to-the-binding-file"></a>Agregar variables para el archivo de enlace

1. Abra el archivo de enlace de la aplicación:

    ![Abra el archivo de enlace](../core/media/biztalk-feature-pack-1-binding-1.png)

2. Busque el elemento que desea cambiar:

    ![Seleccione el elemento](../core/media/biztalk-feature-pack-1-binding-2.png)
    
3. Quitar el valor rellenado y reemplazarlo con usted variables: `$(YourValue)`. Por ejemplo, escriba `$(SendPort1)`: 

    ![Archivo de enlace](../core/media/biztalk-feature-pack-1-binding-3.png)

4. Cuando haya terminado, guarde el archivo de enlace y agregarlo a la plantilla de compilación JSON (pasos de [paso 1: plantilla de aplicación Agregar proyecto & actualización .json](feature-pack-add-application-project.md)).

## <a name="create-the-variables-in-vsts"></a>Cree las variables en VSTS

1. En su cuenta VSTS, seleccione **de compilación y la versión**y seleccione **versiones**.

2. Seleccione el **definición de la versión**y seleccione **Variables**:  

    ![Archivo de enlace](../core/media/vsts-release-variables.png)

3. Seleccione **agregar**y cree los nombres de las variables y valores:   

    ![configurar variables](../core/media/environment-specific-variables.png)

4. **Guardar** los cambios. Cuando se inicia la implementación, los valores se agregan desde el archivo de enlace.

## <a name="see-also"></a>Vea también
[Configurar la implementación automática con Visual Studio Team Services](configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)  
[Configuración del Feature Pack](configure-the-feature-pack.md)