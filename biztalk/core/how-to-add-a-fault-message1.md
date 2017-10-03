---
title: "Cómo agregar un Message1 error | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exceptions, adding messages
- fault messages, adding
- adding, fault messages
- faults, adding messages
ms.assetid: 9d21de6b-c1a5-46e9-a9dc-d6aa7b5fe34b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87ef85460f6ca6aea046ef9efff60fd198664cd1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-fault-message"></a>Cómo agregar un mensaje de error
La primera vez que creó el puerto en el sistema de servidor, contenía una solicitud y una respuesta. Debe agregar un error para capturar la excepción.  
  
### <a name="to-add-a-fault-message"></a>Para agregar un mensaje de error  
  
1.  Haga clic en **operación de puerto**y, a continuación, seleccione un **nuevo mensaje de error**.  
  
     A **error** aparece bajo la **solicitud y respuesta** en el puerto.  
  
2.  En el **Vista orquestación** pantalla, haga clic en **mensajes**y, a continuación, seleccione **nuevo mensaje**.  
  
     De este modo, se crea Message_3, que puede asignar específicamente al error.  
  
3.  Haga clic en **Message_3** para tener acceso a la **propiedades** ventana.  
  
    1.  Establecer el **tipo de mensaje**.  
  
    2.  Seleccione **esquema**y, a continuación, seleccione uno de **ensamblado de referencia**.  
  
         Se abrirá una **Seleccionar tipo de artefacto** ventana.  
  
    3.  Desplácese hacia abajo y seleccione el error completo.  
  
         El nombre es **BTS. SOAP_Envelope_1__1.Fault**. Haga clic en **Aceptar** para aceptar la selección y cerrar la ventana.  
  
4.  Haga clic en el **error** para tener acceso a la **propiedades** ventana.  
  
    1.  Establecer el **tipo de mensaje**.  
  
    2.  Seleccione **esquema** y, a continuación, seleccione uno de **ref** ensamblado.  
  
         Se abrirá una **Seleccionar tipo de artefacto** ventana.  
  
    3.  Desplácese hacia abajo y seleccione el error completo.  
  
         El nombre es **BTS. SOAP_Envelope_1__1.Fault**.  
  
    4.  Haga clic en **Aceptar** para aceptar la selección y cerrar la ventana.  
  
         ![](../core/media/siebeladapter-17-exceptionhandling-addscope.gif "SiebelAdapter_17_ExceptionHandling_AddScope")  
  
5.  Una vez asignado el nombre al error, definirá este nombre en el tipo de objeto de excepción CatchException.  
  
## <a name="see-also"></a>Vea también  
 [Uso de control de excepciones de servidor BizTalk Server](../core/using-biztalk-server-exception-handling2.md)