---
title: Seguridad de InfoPath | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, InfoPath forms
- InfoPath forms, security
ms.assetid: 6ed7b5cc-9801-45a5-8fdb-e5d56dd36435
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef3b1eff57f225d90e7f491f0a8f48ef88f00463
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983581"
---
# <a name="infopath-security"></a>Seguridad de InfoPath
Microsoft [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 usa las firmas XML para permitirle firmar digitalmente un formulario mediante un certificado digital. Las firmas XML define un estándar para las firmas digitales basado en XML que usan para ayudar a proteger los datos contenidos en documentos XML. Las firmas XML es un estándar que se rige por el World Wide Web Consortium (W3C).  
  
 Una firma digital es una marca de segura, electrónica basado en el cifrado de autenticación en una macro o documento. Al firmar digitalmente un [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario, la instancia XML especificada a través del formulario se "marca" con una firma digital (el público de firma síntesis de datos de clave y firmados se escriben en un nodo dedicado en el archivo XML). Esta firma confirma que el documento XML proviene del firmante y no ha sido alterado. [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] Proporciona segura, puede comprobar la firma, firma parcial, cosigning y contrafirmar mediante la compatibilidad con la firma digital mejorada.  
  
 SWIFT [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formularios generados con la utilidad FormGenerator proporcionada por A4SWIFT utilizan el método countersigning de firma digital para permitir que las firmas de countersigners a se apilan unas sobre otras. Esta pila firma countersigning modela el proceso orientado al usuario de creación o edición de un mensaje SWIFT, que tengan el mensaje revisado y aprobado por uno o más revisores y aprobadores y, por último, enviar dicho mensaje sólo después de todas las etapas de un flujo de trabajo haya firmado.  
  
 Los aprobadores, los revisores o reparadores firmar el mensaje, independientemente de si aprobar o rechazar. La firma significa la autenticidad de la respuesta y no indican necesariamente una decisión "aceptada".  
  
 Cuando el [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] se envía el formulario, comprobaciones de validez de los mensajes y que el usuario que firma el formulario está en el rol correcto.  
  
 Si se rechaza el mensaje en cualquier etapa del flujo de trabajo (además de reparación), el mensaje se envía a la etapa de reparación. Si se rechaza el mensaje en la fase de creador o taller de reparación, reparación de mensajes y nuevo envío envía el mensaje a la instancia de orquestación de reparación de mensajes y nuevo envío con las propiedades específicas de marcar el mensaje como rechazado.  
  
 En esta sección se describe cómo controla las firmas digitales en función de las capacidades definidas para un rol de la reparación de mensajes y nuevo envío. La combinación de rol y la capacidad se denomina una "fase" en el flujo de trabajo.  
  
> [!NOTE]
>  La función "crear" está limitada a un creador de único entre todos los departamentos.  
  
 Esta sección contiene:  
  
-   [Crear y etapas de reparación](../../adapters-and-accelerators/accelerator-swift/creating-and-repairing-stages.md)  
  
-   [Fase de comprobación de regeneración de claves](../../adapters-and-accelerators/accelerator-swift/rekey-verification-stage.md)  
  
-   [Fase de aprobación](../../adapters-and-accelerators/accelerator-swift/approval-stage.md)  
  
-   [Distribución de certificados digitales](../../adapters-and-accelerators/accelerator-swift/distributing-digital-certificates.md)