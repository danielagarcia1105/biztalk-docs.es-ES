---
title: "Lista de comprobación: Actualizar los artefactos de una aplicación de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, redeploying
- updating, applications
- redeploying
- checklists, applications
- updating, checklists
- updating
- applications, updating
- applications, redeploying
- applications, checklists
- checklists, redeploying
ms.assetid: 07ea4a2b-4ada-4d04-9eec-604b63b77415
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 321ef2c6c9bbd522c54f5d9352995788d8843455
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-update-the-artifacts-in-a-biztalk-application"></a>Lista de comprobación: Actualizar los artefactos de una aplicación de BizTalk
Siga los pasos de esta lista de comprobación si desea cambiar o actualizar uno o varios artefactos de una aplicación que ya se ha implementado y, a continuación, implementarla de nuevo.  
  
|Paso|Referencia|  
|----------|---------------|  
|Revise las consideraciones importantes para actualizar artefactos en una aplicación.|[Consideraciones importantes para actualizar aplicaciones](../core/important-considerations-for-updating-applications.md)|  
|Asegúrese de que tiene permisos apropiados para realizar la implementación.|[Permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)|  
|Realice todos los cambios necesarios en los ensamblados en Visual Studio. Si va a actualizar un ensamblado que se ejecuta en un entorno de producción, siempre debe incrementar el número de versión del ensamblado. Para obtener información general, vea [actualizar aplicaciones de BizTalk](../core/updating-biztalk-applications.md). A continuación, implemente los ensamblados desde Visual Studio en una aplicación de BizTalk en el entorno de desarrollo.|[Cómo implementar un ensamblado de BizTalk desde Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)|  
|Pruebe todos los artefactos nuevos o modificados y asegúrese de probar también todos aquéllos que dependan de los nuevos o modificados. Durante las pruebas, no olvide tener en cuenta las dependencias que puedan existir entre esta aplicación y otras.|[Tareas de prueba para la implementación de aplicación de BizTalk](../core/testing-tasks-for-biztalk-application-deployment.md)|  
|Agregue, quite o reconfigure artefactos en la aplicación según sea necesario.|[Cómo crear o agregar un artefacto](../core/how-to-create-or-add-an-artifact.md), [cómo quitar un artefacto de una aplicación](../core/how-to-remove-an-artifact-from-an-application.md), [administrar artefactos](../core/managing-artifacts.md)|  
|Exporte la aplicación que contiene los artefactos nuevos o modificados a un archivo .msi. Puede exportar todos los artefactos de la aplicación o únicamente los que desee agregar o actualizar. No olvide que es posible sobrescribir los artefactos de archivo. Si exporta un artefacto de archivo, asegúrese de que se trate de la versión que desea usar en la aplicación.|[Exportar aplicaciones de BizTalk, los enlaces y directivas](../core/exporting-biztalk-applications-bindings-and-policies.md)|  
|Si la actualización va a interferir con la aplicación cuando se ejecute, detenga la aplicación que desee actualizar. Si va a actualizar un ensamblado con una nueva versión, no es preciso reiniciar la aplicación. **Nota:** aunque no es necesario detener una aplicación con el fin de actualizar un artefacto o instalar la aplicación, se recomienda que siempre se detendrá una aplicación al actualizar un artefacto.|[Cómo iniciar y detener una aplicación de BizTalk](../core/how-to-start-and-stop-a-biztalk-application.md)|  
|Importe los artefactos modificados o actualizados del archivo .msi a la aplicación que desee actualizar. Asegúrese de especificar la opción de sobrescritura de los artefactos existentes.|[Cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md)|  
|Instale la aplicación o los artefactos actualizados desde el archivo .msi en todos los equipos que ejecuten la aplicación y también en todos los equipos que ejecuten aplicaciones que dependan de ésta. Si va a actualizar un ensamblado de BizTalk, compruebe que la nueva versión de éste esté instalada en la caché de ensamblados global (GAC) de todos los equipos donde se vaya a ejecutar el ensamblado. En caso contrario, instale el ensamblado en todas las GAC.|[Cómo instalar una aplicación de BizTalk](../core/how-to-install-a-biztalk-application.md), [cómo instalar un ensamblado en la GAC](../core/how-to-install-an-assembly-in-the-gac.md)|  
|Inicie la aplicación.|[Cómo iniciar y detener una aplicación de BizTalk](../core/how-to-start-and-stop-a-biztalk-application.md)|  
|Después de importar un ensamblado que contiene una orquestación, si la aplicación a la que lo va a importar ya contiene un ensamblado con los mismos nombre, token de clave pública y versión, detenga e inicie las instancias de host del host al que esté enlazada la orquestación. De este modo se garantiza que BizTalk Server use la nueva versión del ensamblado.|[Cómo detener una instancia de Host](../core/how-to-stop-a-host-instance.md), [cómo iniciar una instancia de Host](../core/how-to-start-a-host-instance.md)|  
  
## <a name="see-also"></a>Vea también  
 [Implementación de aplicaciones de BizTalk y listas de comprobación de administración](../core/biztalk-application-deployment-and-management-checklists.md)   
 [Actualizar aplicaciones de BizTalk](../core/updating-biztalk-applications.md)