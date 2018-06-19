---
title: Solución de problemas de confirmaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, troubleshooting
- troubleshooting, acknowledgements
ms.assetid: faed356e-f5fc-4920-a9f9-82eca0ad7d67
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ecbbb22498cfd3d451c0b8c75c8e6f4502c2364d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207036"
---
# <a name="troubleshooting-acknowledgments"></a>Solución de problemas de confirmaciones
Soluciona problemas relacionados con [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] confirmaciones.  
  
## <a name="acknowledgments-are-not-generated"></a>No se generan confirmaciones  
 Hay varias causas posibles para las confirmaciones (ACK) no se genera o reciban. Revise la siguiente lista de posibles problemas.  
  
### <a name="symptom"></a>Síntoma  
 No se generan cuando se actualiza la información de entidad [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración para generar confirmaciones.  
  
**Causa posible** : [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] almacena en caché y actualiza la información de configuración de entidad cada 15 minutos.  
  
**Resolución** : espere al menos 15 minutos para la memoria caché actualizar o reiniciar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para cambios surtan efecto inmediatamente.  
  
### <a name="symptom"></a>Síntoma  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]no generar confirmaciones y los errores de eventos aparecen en el registro de eventos.  
  
**Causa posible** : no se puede generar una confirmación cuando un lote en / lote mensaje contiene un campo FHS11 vacío.  
  
**Resolución** : asegúrese de que los mensajes tienen un campo de FHS11 correctamente formateado y rellenado.  
  
### <a name="symptom"></a>Síntoma  
 La aplicación no puede generar o recibir una confirmación.  
  
**Causa posible** : impide que la información incorrecta en el campo MSH3 del mensaje [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] de enviar el mensaje de confirmación.  
  
**Resolución** : asegúrese de que los mensajes tienen un campo de MSH3 correctamente formateado y rellenado.  
  
## <a name="acknowledgments-are-suspended-or-not-routed-to-the-send-party"></a>Confirmaciones se suspende o no se enrute a la entidad de envío  
  
### <a name="symptom"></a>Síntoma  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]envía mensajes a un adaptador bidireccional sin generar confirmaciones.  
  
**Causa posible** : la suscripción de mensaje no está configurada correctamente.  
  
**Resolución** : asegúrese de que las suscripciones de mensaje están presente y configurado correctamente.  
  
## <a name="suspended-acknowledgments"></a>Confirmaciones suspendidas  
  
### <a name="symptom"></a>Síntoma  
 Confirmaciones se suspenden con el mensaje de error "Se encontró en el campo el delimitador" cuando se ha configurado la entidad para que la codificación de caracteres que contiene caracteres delimitadores como @-! $.  
  
**Causa posible** : el mensaje contiene caracteres como un punto (.) o un guión (-). Al generar las confirmaciones, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] incluye "." y "-" para el valor de marca de tiempo.  
  
**Resolución** : deshabilitar la validación en la canalización de envío para evitar estos errores.  
  
## <a name="biztalk-server-generates-an-error-about-missing-ack-when-using-2-way-mllp-adapter"></a>BizTalk Server genera un error acerca de la falta de confirmación cuando se usa el adaptador MLLP de 2 vías  
  
### <a name="symptom"></a>Síntoma  
 Obtiene el error siguiente o uno similar en el registro de eventos:  
  
 "No se pueden recibir la confirmación de red debido al error" excepción de HRESULT: 0xC0C01662 ""  
  
**Causa posible** : utilizas 1-modo de recepción y el puerto de envío de 2 vías, por lo que BizTalk no tiene un puerto de recepción correspondiente para devolver el mensaje recibido desde el puerto de envío de 2 vías.  
  
**Resolución** : Esto es así por diseño, y puede pasar por alto el mensaje de error.  
  
## <a name="see-also"></a>Vea también  
[Solución de problemas y problemas conocidos de HL7](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)