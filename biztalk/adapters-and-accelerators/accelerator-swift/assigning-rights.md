---
title: Asignación de derechos | Microsoft Docs
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
ms.openlocfilehash: 9b736fc7eb84964f9c0e74a3c319c9de1f3a3a44
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989677"
---
# <a name="assigning-rights"></a>Asignación de derechos
En las bibliotecas de documentos para cada grupo de sitio que creó en el tema anterior, se deben conceder los permisos siguientes:  


|                                         Biblioteca de documentos                                         |                                   Grupos de sitio                                   | Permisos de la biblioteca de documentos personalizados para aplicar |
|--------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------|----------------------------------------------|
|                                    Biblioteca de documentos de plantillas                                    | Payments_Creators<br /><br /> Payments_Repairers<br /><br /> Payments_Approvers |                  Ver elementos                  |
|                                     Sin analizar (los detalles a continuación)                                     |                               Payments_Repairers                                |       Ver, insertar, modificar y eliminar elementos       |
|                              Nuevos mensajes de MT SWIFT (los detalles a continuación)                               |                                Payments_Creators                                |       Ver, insertar, modificar y eliminar elementos       |
|                              Nuevos mensajes MX de SWIFT (los detalles a continuación)                               |                                Payments_Creators                                |       Ver, insertar, modificar y eliminar elementos       |
|                                        Payments_Repairers                                        |                               Payments_Repairers                                |       Ver, insertar, modificar y eliminar elementos       |
|                                        Payments_Approvers                                        |                               Payments_Approvers                                |       Ver, insertar, modificar y eliminar elementos       |
| [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Outbox | Payments_Creators<br /><br /> Payments_Repairers<br /><br /> Payments_Approvers |       Ver, insertar, modificar y eliminar elementos       |

## <a name="unparsed-document-library"></a>Biblioteca de documentos sin analizar  
 El [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] el proceso de reparación de mensajes se ocupa de los mensajes que se producirá un error de análisis de una manera especial. Mensajes sin analizar (mensajes que no se puede convertir en XML) se enrutan a la biblioteca de documentos de un único mensaje sin analizar. La biblioteca de documentos sin analizar debe estar restringida para permitir que sólo usuarios específicos, en lugar de todos los grupos tener acceso a la carpeta. Esto garantizará que la carpeta sin analizar es tan segura como sea posible.  

 Los usuarios que tienen permisos para reparar los mensajes sin analizar necesitan permisos de la función de reparación para al menos un departamento definido en la consola de MMC de configuración y también debe estar inscrito en el grupo de NT [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] grupo de usuarios.  

## <a name="new-swift-mt-mx-messages-document-library"></a>Nuevo MT SWIFT / biblioteca de documentos de mensajes MX  
 Las bibliotecas de documentos nuevos mensajes de SWIFT MT y nuevos mensajes de SWIFT MX se crean en el momento de implementar el sitio MRSR. Las bibliotecas de documentos nuevos mensajes de SWIFT MT y nuevos mensajes de SWIFT MX almacenan plantillas nuevas de SWIFT XML o mensajes de "texto reutilizable". Puede utilizar estos mensajes para crear nuevo SWIFT mensajes representados en formato XML de InfoPath. Estos mensajes se cargan en las bibliotecas de documentos nuevos mensajes de SWIFT MT y nuevos mensajes de SWIFT MX por el usuario haciendo clic en el botón de carga en la biblioteca de documentos. Además, puede distribuir las plantillas de nuevos mensajes de SWIFT para restringir el acceso a los usuarios especificados. Para ello, cree primero una nueva biblioteca de documentos y, a continuación, copie las plantillas XML necesarias para la biblioteca de documentos.  

 Para obtener más información acerca de la herramienta FormPublish, consulte [FormPublish herramienta](http://msdn.microsoft.com/09a6ed31-5917-4776-9a5e-955af440cdac) en la sección herramientas.