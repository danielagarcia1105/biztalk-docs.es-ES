---
title: "Agregar una aplicación de BizTalk Server para Visual Studio Team Services | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b2c7a1ff-0f26-45f3-9a9b-4c99a67b51a9
caps.latest.revision: "4"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: d3fc8c0253c8e2517f78c2d60fdc7c74a983bdbd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="add-a-biztalk-server-application-to-visual-studio-team-services"></a>Agregar una aplicación de BizTalk Server para Visual Studio Team Services
Agregar un [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] proyecto VSTS para implementar automáticamente mediante la integración continua.  

**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** , se pueden implementar automáticamente las aplicaciones para su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] entornos con Visual Studio Team Services (VSTS). 

Estos temas se proporciona información general y se enumeran los pasos claves para implementar la solución de Visual Studio para su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]. 

## <a name="prerequisites"></a>Requisitos previos
* Instalar [Feature Pack 1 de](https://www.microsoft.com/download/details.aspx?id=55100) en el[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]
* [Configurar VSTS para la implementación automática](../core/configure-visual-studio-team-services-to-deploy-biztalk-solutions-or-projects.md)
* Conocimientos y experiencia en Git y repositorios en Visual Studio. Si está familiarizado en repositorios y control de versiones, puede tratarse de buenos recursos: 

    [Obtenga información acerca de Git](https://www.visualstudio.com/learn-git/)  
    [GIT y Team Services](https://www.visualstudio.com/docs/git/overview)
* Conocimientos y experiencia de trabajar con proyectos de BizTalk en[!INCLUDE[btsVStudioNoVersion_md](../includes/btsvstudionoversion-md.md)]

## <a name="add-biztalk-project-to-vsts"></a>Agregar proyecto de BizTalk a VSTS
1. En **Visual Studio**, conectarse a su **repositorio de código fuente**, y **clon** a su equipo.
2. Abra o cree una **proyecto de BizTalk** (.btproj).

   > [!NOTE]
   > Puede agregar varios proyectos en la misma solución.
   
3. Agregue un nuevo **proyecto de aplicación de BizTalk Server** (.btaproj).
4. Haga clic en el proyecto en el **el Explorador de soluciones**y seleccione **propiedades**.
5. Configurar la **versión** y las propiedades de conexión para su **Visual Studio Team Services** cuenta.

    ![Visual Studio configuración FP1 BizTalk](../core/media/visual-studio-configuration-fp1-biztalk.png)

6. Agregue todos los ensamblados y los artefactos necesarios para la aplicación.
7. Actualización de la **binding.xml** archivo con la información de enlace correcto.
8. Actualización de la **BizTalkServerInventory.json** con todos los artefactos y el orden correcto para los artefactos que estén instalados en el [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].
9. Haga clic en y **generar** la solución para comprobar si hay algún error. 
10. Cuando la compilación finalice correctamente, haga clic en la solución y seleccione **implementar**.
11. La aplicación debe implementarse automáticamente a su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].

## <a name="see-also"></a>Vea también
[Configurar el Feature Pack](../core/configure-the-feature-pack.md)