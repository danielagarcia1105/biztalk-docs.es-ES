---
title: Crear la FRR ubicación de recepción para la recepción de SWIFT | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, creating
- creating, receive locations
- FRR, creating receive locations
ms.assetid: e10857f4-21cb-4c09-8eed-cb6e9b0a0aa9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e43ac2ac0fab9b2a29a44784032f9d3369833ae2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210156"
---
# <a name="creating-the-frr-receive-location-for-receiving-from-swift"></a>Crear la FRR ubicación de recepción para la recepción de SWIFT.
Para realizar la conciliación de respuesta de FIN, debe crear una ubicación de recepción que recibe un mensaje desde la red SWIFT en A4SWIFT.  
  
> [!NOTE]
>  Es aconsejable configurar dos ubicaciones de recepción para recibir mensajes de AAS: uno para recibir PAN/NaN y otro para todos los demás mensajes de recepción. Para configurar ubicaciones de recepción de los dos, debe recibir mensajes de dos colas de MQSeries en AAS: uno para PAN/NaN y otro para los demás tipos de mensaje.  
  
 **Resumen**  
  
 Crear una ubicación de recepción con las siguientes propiedades y los componentes:  
  
|Propiedad/componente|Configuración|  
|-------------------------|-------------|  
|Puerto de recepción|Puerto unidireccional|  
|Tipo de transporte|MQSeries|  
|Definición de la cola (MQSeries)|Servidor de MQSeries<br />Administrador de cola<br />Cola|  
|Controlador de recepción|BizTalkServerApplication|  
|Canalización de recepción|El A4SWIFT canalización de recepción que haya creado para FRR|  
  
### <a name="to-add-an-frr-receive-location-for-receiving-from-swift"></a>Para agregar una FRR ubicación de recepción para la recepción de SWIFT.  
  
1.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, **grupo de BizTalk**, **aplicaciones**, y **aplicación de BizTalk 1** nodos.  
  
2.  Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.  
  
3.  En el cuadro de diálogo Propiedades de puerto de recepción, en el **nombre** , escriba un nombre para el puerto de recepción, por ejemplo, FRRSWIFTReceivePort.  
  
4.  Haga clic en **aplicar** para enlazar el puerto y, a continuación, haga clic en **Aceptar**.  
  
5.  En la consola de administración, haga clic en **ubicaciones de recepción**, seleccione **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.  
  
6.  En el, seleccione un cuadro de diálogo de puerto de recepción, seleccione el puerto de recepción recién creado y, a continuación, haga clic en **Aceptar**.  
  
7.  En el cuadro de diálogo Propiedades de la ubicación de recepción, en el **nombre** , escriba un nombre para la ubicación de recepción, por ejemplo, FRRSWIFTReceiveLocation.  
  
8.  En el **transporte** sección, para la **tipo** cuadro de texto, seleccione **MQSeries**.  
  
9. Haga clic en **configurar**.  
  
10. En el cuadro de diálogo Propiedades de transporte MQSeries, haga clic en **definición de la cola**y, a continuación, haga clic en el botón de puntos suspensivos (**...** ) botón.  
  
11. En el **definición de la cola** cuadro de diálogo, especifique el servidor de MQSeries, el Administrador de cola y poner en cola. Haga clic en **Aceptar**.  
  
12. En el **propiedades de transporte MQSeries** diálogo cuadro, compruebe que las propiedades según sea necesario. Haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Para obtener más información acerca de las propiedades de transporte de MQSeries, consulte la documentación de MQSeries.  
  
13. En el cuadro de diálogo Propiedades de la ubicación de recepción, para **controlador de recepción**, seleccione **BizTalkServerApplication**.  
  
14. Para **canalización de recepción** sección, seleccione la A4SWIFT canalización de recepción que haya creado para FRR.  
  
15. Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**  
  
16. En el Explorador de BizTalk, haga clic en la ubicación de recepción recién creado y, a continuación, haga clic en **habilitar**.