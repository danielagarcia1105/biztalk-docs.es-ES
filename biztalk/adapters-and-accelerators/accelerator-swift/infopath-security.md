---
title: Seguridad de InfoPath | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, InfoPath forms
- InfoPath forms, security
ms.assetid: 6ed7b5cc-9801-45a5-8fdb-e5d56dd36435
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ec5478af7c404840bf1c5c80be5520e405bd26a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="infopath-security"></a>Seguridad de InfoPath
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 utiliza firmas XML para permitirle firmar digitalmente un formulario con un certificado digital. Las firmas XML define un estándar para las firmas digitales basado en XML que usan para ayudar a proteger los datos contenidos en documentos XML. Las firmas XML es un estándar regido por el World Wide Web Consortium (W3C).  
  
 Una firma digital es una marca de electrónica, basado en el cifrado segura de autenticación en una macro o documento. Al firmar digitalmente un [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario, la instancia XML especificada a través del formulario se "marca" con una firma digital (firma público resumen de datos de clave y firmados se escribe en un nodo dedicado en el archivo XML). Esta firma confirma que el documento XML original creado por el firmante y no se han modificado. [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]proporciona no segura, puede comprobar la firma, firma parcial, cosigning y contrafirmar mediante la compatibilidad mejorada de firma digital.  
  
 SWIFT [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formularios generados con la utilidad FormGenerator proporcionada por A4SWIFT utilizar el método countersigning de firma digital para permitir que las firmas de countersigners estar apilados unos encima de otros. Esta pila firma countersigning modela el proceso de crear o editar un mensaje SWIFT, que tengan el mensaje revisado y aprobado por uno o más revisores y aprobadores y finalmente enviar ese mensaje después de todas las fases de un flujo de trabajo centrado en los usuarios haya firmado.  
  
 Talleres de reparación, revisores o aprobadores firmar el mensaje independientemente de si aprobarlo o rechazarlo. La firma significa la autenticidad de la respuesta y no implica necesariamente una decisión "aceptada".  
  
 Cuando el [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] se envía el formulario, comprueba la validez de los mensajes y que el usuario firma el formulario está en el rol correcto.  
  
 Si se rechaza el mensaje en cualquier fase de un flujo de trabajo (además de la reparación), el mensaje se envía a la etapa de reparación. Si se rechaza el mensaje en la fase de taller de reparación o creador, reparación de mensajes y nuevo envío envía el mensaje a la instancia de orquestación de reparación de mensajes y nuevo envío con propiedades específicas de marcar el mensaje como rechazado.  
  
 Esta sección describe cómo reparación de mensajes y nuevo envío controla las firmas digitales en función de las capacidades definidas para un rol. La combinación de rol y capacidad se denomina una "fase" en el flujo de trabajo.  
  
> [!NOTE]
>  La función "crear" está limitada a un creador de único entre todos los departamentos.  
  
 Esta sección contiene:  
  
-   [Crear y etapas de reparación](../../adapters-and-accelerators/accelerator-swift/creating-and-repairing-stages.md)  
  
-   [Regenerar la fase de comprobación](../../adapters-and-accelerators/accelerator-swift/rekey-verification-stage.md)  
  
-   [Fase de aprobación](../../adapters-and-accelerators/accelerator-swift/approval-stage.md)  
  
-   [Distribución de certificados digitales](../../adapters-and-accelerators/accelerator-swift/distributing-digital-certificates.md)