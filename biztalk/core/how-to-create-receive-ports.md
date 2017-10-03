---
title: "Cómo crear puertos de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, receive
- receive ports
- creating receive ports
ms.assetid: d390320e-12f1-4ead-b608-60bc1e273477
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1ca5727422fd7519443cc290d35d0c2e24d499f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-receive-ports"></a>Cómo crear puertos de recepción
Siga estos pasos para crear un puerto de recepción mediante Visual Studio.  
  
### <a name="to-create-a-receive-port"></a>Para crear un puerto de recepción  
  
1.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el deseado aplicación.  
  
2.  Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puertos de recepción unidireccionales**.  
  
3.  En el **propiedades de puerto de recepción** ventana, en la **General** página, realice lo siguiente:  
  
    1.  En el **nombre** , escriba `ReceiveFromTIBCORV`.  
  
    2.  En el **autenticación** cuadro del grupo, especifique cómo se administran los mensajes al utilizar la autenticación.  
  
    3.  Seleccione el **habilitar enrutamiento para mensajes con errores** casilla de verificación.  
  
4.  En el **ubicaciones de recepción** página, realice lo siguiente:  
  
    1.  Haga clic en **Nueva**.  
  
    2.  En el **ubicaciones de recepción** ventana, en la **General** página, escriba el **nombre** de la ubicación de recepción.  
  
    3.  Desde el **tipo** lista desplegable, seleccione el tipo de transporte y desde el **controlador de recepción** lista desplegable, seleccione la dirección de transporte.  
  
    4.  Desde el **canalización de recepción** lista desplegable, seleccione la canalización de recepción.  
  
    5.  En el **programación** página, seleccione la **fecha de inicio** y **fecha de finalización** para restringir la recepción de documentos.  
  
    6.  Seleccione el **habilitar ventana de servicio** casilla de verificación.  
  
    7.  Haga clic en **Aceptar**.  
  
5.  En el **asignaciones de entrada** , seleccione las asignaciones de entrada para transformar documentos en el puerto seleccionado.  
  
6.  En el **seguimiento** página, seleccione el seguimiento de cuerpos de mensaje y el seguimiento de propiedades de mensaje deseado.  
  
7.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Controladores de recepción de creación TIBCO Rendezvous](../core/creating-tibco-rendezvous-receive-handlers.md)