---
title: Cómo quitar un artefacto de una aplicación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- artifacts, deleting
- applications, modifying
- applications, artifacts
- modifying, applications
- deleting, artifacts
ms.assetid: c528be0b-0b1a-4c5f-acd2-7355da91a253
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25d57c41311cef12a33685dcc4c8aacd85290b7f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254924"
---
# <a name="how-to-remove-an-artifact-from-an-application"></a>Cómo quitar un artefacto de una aplicación
Al quitar o eliminar un artefacto, se elimina de las bases de datos del servidor BizTalk Server, de modo que ya no aparece en la consola de administración ni en la lista de artefactos de una aplicación generados por el comando BTSTask ListApp. No quita el artefacto del Registro de Windows, de la caché de ensamblados global (GAC), de un directorio virtual o del sistema de archivos, si se encuentra en alguna de estas ubicaciones. En el caso de los puertos de envío, grupos de puertos de envío, puertos de recepción y de las ubicaciones de recepción, que solo se encuentran en la base de datos de administración de BizTalk, esta operación elimina el artefacto completamente. Para obtener información general, vea [¿qué ocurre cuando los artefactos se agregan y se eliminan](../core/what-happens-when-artifacts-are-added-and-removed.md)  
  
 Quitar o eliminar un artefacto puede tener distintos efectos en el funcionamiento de una aplicación según el tipo de artefacto. Para obtener más información e instrucciones acerca de cómo quitar o eliminar un tipo de artefacto concreto, consulte el tema correspondiente del modo siguiente:  
  
-   [Cómo quitar una orquestación de una aplicación](../core/how-to-remove-an-orchestration-from-an-application.md)  
  
-   [Cómo eliminar un puerto de envío](../core/how-to-delete-a-send-port.md)  
  
-   [Cómo eliminar un grupo de puertos de envío](../core/how-to-delete-a-send-port-group.md)  
  
-   [Cómo eliminar un puerto de recepción](../core/how-to-delete-a-receive-port.md)  
  
-   [Cómo eliminar una ubicación de recepción](../core/how-to-delete-a-receive-location.md)  
  
-   [Cómo quitar una directiva de una aplicación y el grupo de BizTalk](../core/how-to-remove-a-policy-from-an-application-and-the-biztalk-group.md)  
  
-   [Cómo quitar un esquema de una aplicación](../core/how-to-remove-a-schema-from-an-application.md)  
  
-   [Cómo quitar una asignación de una aplicación](../core/how-to-remove-a-map-from-an-application.md)  
  
-   [Cómo quitar un ensamblado de BizTalk desde una aplicación](../core/how-to-remove-a-biztalk-assembly-from-an-application.md)  
  
-   [Cómo quitar una secuencia de comandos previa y posteriores al procesamiento de una aplicación](../core/how-to-remove-a-pre-or-post-processing-script-from-an-application.md)  
  
-   [Cómo quitar un ensamblado. NET, certificado ni ningún otro artefacto de recurso de una aplicación](../core/remove-a-net-assembly-certificate-or-resource-artifact-from-an-application.md)  
  
## <a name="see-also"></a>Vea también  
 [Creación y modificación de las aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md)   
 [RemoveResource (comando)](../core/removeresource-command.md)