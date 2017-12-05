---
title: "Lea la problemas conocidos de instalación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 245379f2-4048-4803-83ea-38dc23eb1a81
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6641e7974a0e1872b71794af6553d708e9619dd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="read-the-installation-known-issues"></a>Lea la problemas conocidos de instalación
[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]experimentan problemas conocidos enumerados en las secciones siguientes.  
  
## <a name="swift-does-not-support-stress-testing-on-integration-test-bed-itb-and-swiftnet-stub-environment"></a>SWIFT no admite pruebas de esfuerzo en el entorno de pruebas de integración (ITB) y el entorno de código auxiliar de SWIFTNet  
 El ITB no proporciona el contrato de nivel de servicio (SLA) en cuanto a rendimiento y no puede garantizar que los datos son completamente transmitidos o coherente. Debe prueba de carga de red de su implementación en producción en el entorno de prueba piloto.  
  
 Además, debe asegurarse de que todos los nodos (servidores, líneas y ancho de banda) están configurados correctamente para evitar la pérdida de datos. Siguientes son la capacidad de proceso de ejemplo típica:  
  
-   Enviar interactuar/Fileact equipo acentuado: 20 mensajes/minuto  
  
-   Recepción interactuar/Fileact equipo acentuado: 300-400 mensajes por minuto  
  
 Para obtener más información, consulte la documentación de SWIFT.  
  
## <a name="messages-not-pushed-when-queue-is-open"></a>No se inserta cuando se abre la cola de mensajes  
 Cuando se usa InterAct o almacenamiento de FileAct y el modo de avance (SnF), si está abierta la sesión con la cola y no se extraen los mensajes, debe reiniciar SNLreceiver.exe. Esto evita que un problema con SWIFT que se puede producir ocasionalmente.  
  
## <a name="you-must-use-cdata-when-passing-characters-like--and--in-message"></a>Se debe usar CDATA al pasar caracteres como "<" y "&" en el mensaje  
 El término CDATA se utiliza sobre los datos de texto que no se deben analizar el analizador XML.  Caracteres como "<" y "&" no son válidos en los elementos XML. "<", se generará un error porque el analizador lo interpreta como el inicio de un nuevo elemento. "&", se generará un error porque el analizador lo interpreta como el inicio de una entidad de caracteres. El analizador omite todo el contenido dentro de una sección CDATA. Una sección CDATA comienza con "\<! [ CDATA ["y termina con"]]\>"  
  
## <a name="you-must-use-passthrough-pipelines-with-payload-only-mode"></a>Debe utilizar las canalizaciones Passthrough con modo de solo carga  
 Si se usa el modo de solo carga para el adaptador de InterAct, debe utilizar paso a través de canalizaciones de envío y puertos de recepción si no se utiliza canalizaciones personalizadas.  
  
## <a name="multiple-security-contexts-not-created-swiftnet-stub-computer"></a>Varios contextos de seguridad no creados (código auxiliar de SWIFTNet equipo)  
 En un equipo de código auxiliar SWIFTNet, no se crean varios contextos de seguridad para puertos de envío diferentes. Varios contextos de seguridad se crean en ITB.