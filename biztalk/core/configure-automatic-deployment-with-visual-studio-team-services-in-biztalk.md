---
title: "Configurar la implementación automática con Visual Studio Team Services en BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57f769bb-5105-43e2-9096-ed54cdf82b90
caps.latest.revision: "8"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 23d79eae3bd89a572a919cfeff800178f9163796
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-automatic-deployment-with-visual-studio-team-services-in-biztalk-server"></a>Configurar la implementación automática con Visual Studio Team Services en BizTalk Server
Implementar automáticamente [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] aplicaciones mediante Visual Studio Team Services. 

**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** , [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] proporciona una implementación automática mejorada y experiencia con aplicaciones lifecycle management (ALM). 

En esta sección se muestra cómo configurar VSTS con [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]y agregar su primera aplicación para la implementación.

## <a name="before-you-begin"></a>Antes de empezar

* Tener una cuenta de Visual Studio Team Services (VSTS) listo. ¿No tiene? [Registrarse para obtener Visual Studio Team Services](https://www.visualstudio.com/docs/setup-admin/team-services/sign-up-for-visual-studio-team-services).
* Si ya tiene un agente de VSTS instalado en el equipo de BizTalk, el agente existente se sobrescribe con el agente de VSTS más reciente. Quizás tenga que actualizar su [servicio VSTS para alinearlo con el nuevo agente](https://www.visualstudio.com/docs/build/actions/agents/v2-windows#replace-an-agent).
* Implementación automática con VSTS se realiza en una [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] en el grupo. Asegúrese de que el equipo tiene Visual Studio y la [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] instalado SDK y herramientas de programadores. Consulte la [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] [requisitos de hardware y software](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).

## <a name="next-steps"></a>Pasos siguientes
[Configurar VSTS para la implementación automática](../core/configure-visual-studio-team-services-to-deploy-biztalk-solutions-or-projects.md)

[Configurar la plantilla JSON](../core/configure-the-json-template-for-automatic-deployment.md)

[Configurar las variables y tokens de entorno](../core/configure-environmental-tokens-and-variables-for-automatic-deployment.md)

[Agregar una aplicación de BizTalk a VSTS](../core/add-a-biztalk-server-application-to-visual-studio-team-services.md)