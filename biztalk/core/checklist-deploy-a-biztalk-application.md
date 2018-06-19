---
title: 'Lista de comprobación: Implementar una aplicación de BizTalk | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- checklists, deploying
- applications, deploying
- deploying [applications], checklists
- checklists, applications
- applications, checklists
ms.assetid: 0f936475-eea7-49b0-a4ea-9488b4ce3847
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76384f4684d22d2e8293013598d82a25a0543876
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232788"
---
# <a name="checklist-deploy-a-biztalk-application"></a>Lista de comprobación: Implementar una aplicación de BizTalk
|Paso|Referencia|  
|----------|---------------|  
|Obtenga información acerca de las características de implementación y la funcionalidad de las aplicaciones de BizTalk. También puede ser conveniente estudiar cómo usar los archivos de enlace para agilizar y facilitar la implementación de aplicaciones.|[Descripción de la implementación de aplicaciones de BizTalk y administración](../core/understanding-biztalk-application-deployment-and-management.md), [archivos de enlace e implementación de aplicaciones](../core/binding-files-and-application-deployment.md)|  
|Asegúrese de que tiene permisos apropiados para realizar la implementación.|[Permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)|  
|En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], establezca las propiedades de implementación para cada proyecto de la solución de BizTalk. Estas propiedades incluyen el nombre del servidor de la base de datos y la base de datos de administración de BizTalk para el grupo, así como el nombre de la aplicación de BizTalk de destino. También puede habilitar la posibilidad de una nueva implementación y especificar la opción de reinicio automático de las instancias del host cuando se vuelva a implementar.|[Cómo establecer propiedades de implementación en Visual Studio](../core/how-to-set-deployment-properties-in-visual-studio.md)|  
|Implemente ensamblados de BizTalk en la aplicación de destino desde [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].|[Cómo implementar un ensamblado de BizTalk desde Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)|  
|Complete la aplicación de BizTalk, agregando elementos tales como ensamblados .NET, archivos Léame, archivos de enlace específicos del entorno y secuencias comandos, y configurando puertos y ubicaciones de recepción. También deberá agregar las infraestructuras necesarias, tales como las ubicaciones de entrega de archivos, al equipo host.|[Creación y modificación de las aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md), [archivos de enlace e implementación de aplicaciones](../core/binding-files-and-application-deployment.md)|  
|Exporte la aplicación de BizTalk a un archivo MSI que se usará para importar la aplicación a otro grupo de BizTalk, y también instale la aplicación en los equipos que vayan a ejecutarla.|[Cómo exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md)|  
|Importe el archivo MSI para crear la aplicación de BizTalk en el grupo de BizTalk de destino. Si ha agregado archivos de enlace específicos del entorno a la aplicación, puede seleccionar los enlaces que se aplicarán al importar.|[Cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md)|  
|Realice las modificaciones adicionales a la aplicación, para que se ejecute en el entorno de destino, como cambiar la configuración de los puertos. Si ha realizado algún cambio, exporte la aplicación a un archivo MSI que se usará para instalar la aplicación en los equipos que la ejecutarán. También puede importar la aplicación a otros grupos de BizTalk donde quiera implementarla.|[Creación y modificación de las aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md), [cómo agregar un archivo de enlace a una aplicación](../core/how-to-add-a-binding-file-to-an-application2.md), [cómo exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md), [cómo importar un BizTalk Aplicación](../core/how-to-import-a-biztalk-application.md)|  
|Con el archivo MSI, instale la aplicación en todos los equipos que la van a ejecutar, e iníciela desde la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].|[Cómo instalar una aplicación de BizTalk](../core/how-to-install-a-biztalk-application.md)|  
  
## <a name="see-also"></a>Vea también  
 [Implementación de aplicaciones de BizTalk y listas de comprobación de administración](../core/biztalk-application-deployment-and-management-checklists.md)