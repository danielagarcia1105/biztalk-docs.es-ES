---
title: Lea la problemas conocidos de la instalación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 245379f2-4048-4803-83ea-38dc23eb1a81
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4bc572cc18ca7d9d5515fe9f189287df5d1440f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022954"
---
# <a name="read-the-installation-known-issues"></a>Lea la problemas conocidos de la instalación
[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] experimentan problemas conocidos enumerados en las secciones siguientes.  
  
## <a name="swift-does-not-support-stress-testing-on-integration-test-bed-itb-and-swiftnet-stub-environment"></a>SWIFT no admite pruebas de esfuerzo en el banco de pruebas de integración (ITB) y el entorno de código auxiliar de SWIFTNet  
 El ITB no proporciona el acuerdo de nivel de servicio (SLA) en cuanto a rendimiento y no puede garantizar que los datos están completamente transmitidos o coherente. Debe prueba de esfuerzo de la implementación en la producción de red en el entorno piloto.  
  
 Además, debe asegurarse de que todos los nodos (servidores, líneas y ancho de banda) están configuradas correctamente para evitar la pérdida de datos. A continuación se muestran los rendimientos de ejemplo típica:  
  
- Enviar interactuar/Fileact equipo acentuado: 20 mensajes/minuto  
  
- De recepción de Fileact/interactuar en el equipo acentuado: 300-400 mensajes/minuto  
  
  Para obtener más información, consulte la documentación de SWIFT.  
  
## <a name="messages-not-pushed-when-queue-is-open"></a>No se han analizado cuando se abre la cola de mensajes  
 Cuando se usa la interacción o FileAct Store y el modo de avance (SnF), si la sesión con la cola está abierta y no se extraen los mensajes, a continuación, debe reiniciar SNLreceiver.exe. Esto evita un problema con SWIFT que se puede producir ocasionalmente.  
  
## <a name="you-must-use-cdata-when-passing-characters-like--and--in-message"></a>Se debe usar CDATA al pasar caracteres como "<" y "&" en el mensaje  
 El término CDATA se utiliza sobre los datos de texto que no se deben analizar mediante el analizador XML.  Caracteres como "<" y "&" no son válidas en los elementos XML. "<", se generará un error porque el analizador lo interpreta como el inicio de un nuevo elemento. "&", se generará un error porque el analizador lo interpreta como el comienzo de una entidad de caracteres. El analizador omite todo el contenido dentro de una sección CDATA. Una sección CDATA comienza con "\<! [ CDATA ["y termina con"]]\>"  
  
## <a name="you-must-use-passthrough-pipelines-with-payload-only-mode"></a>Debe utilizar las canalizaciones Passthrough con modo de sólo carga  
 Si usas el modo de sólo carga para el adaptador de InterAct, debe utilizar las canalizaciones de paso a través en ambos el envío y puertos de recepción si no usa las canalizaciones personalizadas.  
  
## <a name="multiple-security-contexts-not-created-swiftnet-stub-computer"></a>Varios contextos de seguridad no creados (código auxiliar de SWIFTNet equipo)  
 En un equipo de código auxiliar SWIFTNet, no se crean varios contextos de seguridad para los puertos de envío diferentes. Varios contextos de seguridad se crean en ITB.