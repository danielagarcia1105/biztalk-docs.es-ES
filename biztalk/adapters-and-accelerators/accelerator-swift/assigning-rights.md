---
title: Asignación de derechos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- user accounts, assigning permissions
- security, user accounts
- document library, new messages
- document library, unparsed
- messages, document library
- privileges
- permissions
- unparsed document library
- security, permissions
ms.assetid: cee44240-aa00-4080-9e7f-728b2421102b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a0d152442bf375c43d371e5ca5c3fcfb9dc5939
ms.sourcegitcommit: 3371ffd8ceca02e2b3715d53a1e0c0a59045912e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2018
ms.locfileid: "34848964"
---
# <a name="assigning-rights"></a>Asignación de derechos
Deben conceder los siguientes permisos en las bibliotecas de documentos para cada grupo de sitio que creó en el tema anterior:  
  
|Biblioteca de documentos|Grupos de sitio|Permisos de la biblioteca de documento personalizadas que se aplica|  
|----------------------|-----------------|--------------------------------------------------|  
|Biblioteca de documentos de plantillas|Payments_Creators<br /><br /> Payments_Repairers<br /><br /> Payments_Approvers|Ver elementos|  
|Sin analizar (detalles a continuación)|Payments_Repairers|Ver, insertar, editar y eliminar elementos|  
|Nuevos mensajes de MT SWIFT (detalles a continuación)|Payments_Creators|Ver, insertar, editar y eliminar elementos|  
|Nuevos mensajes de MX de SWIFT (detalles a continuación)|Payments_Creators|Ver, insertar, editar y eliminar elementos|  
|Payments_Repairers|Payments_Repairers|Ver, insertar, editar y eliminar elementos|  
|Payments_Approvers|Payments_Approvers|Ver, insertar, editar y eliminar elementos|  
|[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Outbox|Payments_Creators<br /><br /> Payments_Repairers<br /><br /> Payments_Approvers|Ver, insertar, editar y eliminar elementos|  
  
## <a name="unparsed-document-library"></a>Biblioteca de documentos sin analizar  
 El [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] trata el proceso de reparación de mensajes con mensajes que generan errores de análisis de una manera especial. Sin analizar mensajes (que no se puede traducir a XML) se enrutan a la biblioteca de documentos de un único mensaje sin analizar. La biblioteca de documentos sin analizar debe estar restringida para permitir que sólo usuarios específicos, en lugar de todos los grupos tener acceso a la carpeta. Esto garantizará que la carpeta sin analizar es lo más segura posible.  
  
 Los usuarios que tienen permisos para reparar los mensajes sin analizar necesita permisos para la función de reparación para al menos un departamento definido en la consola de configuración de MMC y también debe estar inscrito en el grupo de NT [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] grupo de usuarios.  
  
## <a name="new-swift-mt-mx-messages-document-library"></a>Nueva MT SWIFT / biblioteca de documentos de mensajes MX  
 Las bibliotecas de documentos nuevos mensajes de SWIFT MT y mensajes de MX de SWIFT nuevos se crean en el momento de implementar el sitio MRSR. Las bibliotecas de documentos nuevos mensajes de SWIFT MT y nuevos mensajes de SWIFT MX almacenan nuevas plantillas de SWIFT XML o mensajes de "reutilizable". Puede utilizar estos mensajes para crear nuevo SWIFT mensajes representados en formato XML de InfoPath. Estos mensajes se cargan en las bibliotecas de documentos nuevos mensajes de SWIFT MT y nuevos mensajes de SWIFT MX por el usuario haciendo clic en el botón de carga en la biblioteca de documentos. Además, podrá distribuir las plantillas de nuevo mensaje SWIFT para restringir el acceso a los usuarios especificados. Para ello, primero cree una nueva biblioteca de documentos y, a continuación, copie las plantillas XML necesarias para la biblioteca de documentos.  
  
 Para obtener más información acerca de la herramienta FormPublish, consulte [FormPublish herramienta](http://msdn.microsoft.com/09a6ed31-5917-4776-9a5e-955af440cdac) en la sección de herramientas.