---
title: "Reparación de mensajes sin analizar | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unparsed messages
- repairing messages, unparsed messages
- messages, unparsed messages
ms.assetid: cc061243-3539-4407-a096-71a3feded1c5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de427afc854bf782f69a8c0428a874c61ffb5c4f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="repairing-unparsed-messages"></a>Reparación de mensajes sin analizar
Si el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Desensamblador no puede analizar un mensaje, puede reparar ese mensaje. Hacer esto en un [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario desde el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] sitio MRSR. Sin embargo, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] procesa ese mensaje de manera diferente a un mensaje reparado que un error de validación de XML o BRE.  
  
 Si un mensaje o un lote, no se puede analizar, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] lo marca como [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed = True, con un número de error de análisis mayor que 0. El cuerpo del mensaje permanece en forma de archivo sin formato, que incluye en un contenedor XML. Si la regla de reparación se establece para permitir el procesamiento de errores de análisis, el mensaje se envía a la Bandeja de entrada sin analizar para el procesamiento con el formato sin analizar.  
  
 Hay solo una bandeja de entrada sin analizar para todos los usuarios y todos los departamentos, porque [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] no se puede tener acceso a los datos sobre el mensaje aparte de ubicación de recepción original. Como resultado, para reparar un mensaje sin analizar, un usuario debe tener la capacidad de reparación y debe estar asociado con la función de reparación en todos los departamentos.  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]Muestra el mensaje sin analizar en el área de texto de la Unparsed [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario. Para corregir el problema de análisis, puede introducir o eliminar caracteres según sea necesario. Una vez que se envía, el mensaje es extraído del contenedor de XML y se vuelven a enviar a través de la canalización de recepción SWIFT. Si el análisis se realice correctamente, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] procesa el mensaje como lo haría con cualquier otro mensaje.  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]no procesa un mensaje sin analizar que haya corregido a través de un flujo de trabajo de reparación completa. [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]manda no comprobados y no aprobadas. Al firmar un mensaje sin analizar reparado y, a continuación, enviarla, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] no ejecutar la validación de BRE ni comprueba el departamento, sino que envía el mensaje directamente a la canalización de envío. Si esa canalización no puede procesar el mensaje, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] envía para el proceso de reparación.  
  
 Este proceso le permite corregir los mensajes con formato incorrecto de otro sistema. Sin embargo, debe tener cuidado cuando se corrigen los problemas de análisis. Cuando [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] controla un mensaje sin analizar, no valida el mensaje. Reparación sin analizar no está definida como un rol, por lo que cualquier persona puede realizar este proceso. Dado que un mensaje sin analizar no pertenecen a cualquier departamento, la única seguridad que proporciona acceso a ellos es las ACL en la Bandeja de entrada sin analizar. [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]También no conserva el original ubicación de recepción de un mensaje sin analizar como una propiedad de contexto del mensaje.  
  
 Puede escribir una validación personalizada que se realizarán en el mensaje reparado sin analizar. También puede escribir una suscripción para enviar un mensaje sin analizar reparado a la canalización de archivo original.  
  
 Para que el mecanismo de reparación para que funcione en los mensajes sin analizar, debe agregar el esquema EnvelopeUnparsedMessage.xsd al ensamblado que contiene los esquemas de mensaje. Para obtener más información, consulte [implementar esquemas de A4SWIFT](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md).