---
title: Configurar la implementación automática con Visual Studio Team Services | Documentos de Microsoft
description: Instalar BizTalk Feature Pack para usar la administración del ciclo de vida de aplicaciones con VSTS para implementar las aplicaciones en diferentes entornos de BizTalk.
ms.custom: ''
ms.date: 11/20/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57f769bb-5105-43e2-9096-ed54cdf82b90
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d135960143fed33d1ce4847c681f5b1134489b65
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
ms.locfileid: "25497885"
---
# <a name="configure-automatic-deployment-with-visual-studio-team-services-in-biztalk-server"></a>Configurar la implementación automática con Visual Studio Team Services en BizTalk Server

## <a name="overview"></a>Información general

**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** , [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] proporciona una implementación automática mejorada y experiencia con aplicaciones lifecycle management (ALM). 

**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2**, hemos mejorado esta característica:

* En Visual Studio, establezca el **nombre de la aplicación** de la aplicación de BizTalk
* Además de usar una implementación basada en agente, también puede usar [grupos de implementación](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index) para implementar las aplicaciones de BizTalk en varios servidores
* En la tarea de versión, puede instalar la aplicación de BizTalk y especifique el equipo de administración de BizTalk y la ruta de acceso al paquete de implementación

Con Visual Studio Team Services, puede implementar automáticamente [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] aplicaciones para diferentes entornos de BizTalk. 

Por lo general, hay dos roles implicados:

- Programador de BizTalk crea la aplicación y genera de forma local. A continuación, comprueba si la aplicación en Git o Control de versiones de Team Foundation.
- Administrador VSTS crea las definiciones de compilación y versión e implementa en la aplicación de BizTalk para diferentes entornos (desarrollo, UAT, producción).

Si nunca ha utilizado VSTS, este tutorial puede ser un desafío. Requieren ciertos conocimientos de git, incluida la clonación e insertar los cambios. 

Le mostramos cómo configurar VSTS con [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]y agregar su primera aplicación para la implementación. Se recomienda que haga referencia a la [instrucciones de VSTS](https://docs.microsoft.com/vsts/user-guide/), tal y como se cambia la UI VSTS. 

## <a name="before-you-begin"></a>Antes de empezar

* Tener una cuenta de Visual Studio Team Services (VSTS) listo. ¿No tiene? [Registrarse para obtener Visual Studio Team Services](https://www.visualstudio.com/docs/setup-admin/team-services/sign-up-for-visual-studio-team-services).
* Si ya tiene un agente de VSTS instalado en el equipo de BizTalk, el agente existente se sobrescribe con el agente de VSTS más reciente. Quizás tenga que actualizar su [servicio VSTS para alinearlo con el nuevo agente](https://www.visualstudio.com/docs/build/actions/agents/v2-windows#replace-an-agent).
* Con Feature Pack 1, se realiza la implementación automática con VSTS en uno [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] en el grupo. Asegúrese de que el equipo tiene Visual Studio y la [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] instalado SDK y herramientas de programadores. Consulte la [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] [requisitos de hardware y software](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).
* Con Feature Pack 2, es posible la implementación automática con VSTS mediante [grupos de implementación](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/howto-deployment-groups). Uso de grupos de implementación, puede implementar las aplicaciones en varios servidores de BizTalk dentro del grupo de implementación.

## <a name="prerequisites"></a>Requisitos previos

* Instalar [Feature Pack 2 de](https://aka.ms/bts2016fp2) en el[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]
* Algunos experiencia y conocimientos de crear y trabajar con definiciones de VSTS. Si está familiarizado en VSTS, puede tratarse de buenos recursos: 

  [Introducción a Visual Studio Team Services](https://www.visualstudio.com/docs/overview)  
  [Elemento de configuración/CD para principiantes](https://www.visualstudio.com/docs/build/get-started/ci-cd-part-1)

## <a name="get-started"></a>Introducción
[Paso 1: Agregar el proyecto de la aplicación y actualizar la plantilla .json](feature-pack-add-application-project.md)  

[Paso 2: Crear el token VSTS e instalar al agente de compilación](feature-pack-create-vsts-token.md)

[Paso 3: Crear la compilación y las definiciones de la versión](feature-pack-add-build-release-definitions.md)

[Configurar las variables y tokens de entorno](configure-environmental-tokens-and-variables-for-automatic-deployment.md)