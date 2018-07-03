---
title: Habilitación de la recepción de varios intercambios en un único mensaje | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c98bcd2e-495a-49d8-a471-6e23b1e161f9
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77af57fb4a72e2e0c039b512d4e6f30659ccedd5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006853"
---
# <a name="enabling-the-receiving-of-multiple-interchanges-in-a-single-message"></a>Habilitar la recepción de varios intercambios en un único mensaje
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede procesar un mensaje que contiene varios intercambios. Por ejemplo, un mensaje X12 incluye varios encabezados ISA y finalizadores IEA. Por otro lado, un mensaje EDIFACT incluye varios encabezados UNA/UNB y finalizadores UNZ.  
  
 Para habilitar el Desensamblador EDI en la canalización EdiReceive o AS2EdiReceive para que analice varios intercambios en un único mensaje, debe establecer el **DetectMID** propiedad de canalización **True**. (MID significa desensamblado de varios intercambios). Esta propiedad está establecida en True de forma predeterminada.  
  
 Cuando la canalización de recepción que incluye el desensamblador EDI recibe un mensaje con varios intercambios, el desensamblador analizará cada uno de los intercambios, desde el encabezado hasta el finalizador del intercambio. Este procesamiento se realiza de acuerdo con las reglas siguientes:  
  
- Todos los intercambios del mismo mensaje deben estar codificados de la misma forma, bien X12 bien EDIFACT. Si el mensaje contiene intercambios con más de un tipo de codificación, el desensamblador EDI procesará todos los intercambios con el mismo tipo de codificación como el primer intercambio del mensaje. El desensamblador omitirá en el primer intercambio todos los intercambios que cuenten con otro tipo de codificación.  
  
- El desensamblador EDI omitirá todos los caracteres existentes entre el finalizador de un intercambio y el encabezado del siguiente.  
  
- Si habilita la autenticación seleccionando el **eliminar mensajes si hay errores de autenticación** o **conservar mensajes si hay errores de autenticación** propiedad para el puerto de recepción y, a continuación, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] le suspender el mensaje completo si se produce un error en cualquiera de los distintos intercambios del mensaje.  
  
- Si habilita la autenticación y alguno de los intercambios del mismo mensaje no se resuelve para un acuerdo, se suspenderán todos los intercambios del mensaje y no se devolverá ninguna confirmación, ni siquiera para los intercambios que sí se resolvieron para un acuerdo.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-enable-the-receiving-of-multiple-interchanges-in-a-message"></a>Para habilitar la recepción de varios intercambios en un mensaje  
  
1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **ubicaciones de recepción** nodo, haga la ubicación de recepción que desea habilitar para que reciba varios intercambios en un único mensaje y, a continuación, haga clic en  **Propiedades**.  
  
2. Haga clic en el botón de puntos suspensivos que aparece junto a la canalización de recepción (que debe ser EdiReceive o AS2EdiReceive).  
  
3. En el **configurar canalización** cuadro de diálogo, establezca el **DetectMID** propiedad de canalización **True**.  
  
4. Haga clic en **Aceptar**, a continuación, haga clic en **Aceptar** nuevo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de puertos para una solución EDI](../core/configuring-ports-for-an-edi-solution.md)