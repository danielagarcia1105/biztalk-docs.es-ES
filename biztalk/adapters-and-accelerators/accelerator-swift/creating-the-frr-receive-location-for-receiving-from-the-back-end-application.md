---
title: Crear la FRR ubicación de recepción para recibir de la aplicación de Back-End | Documentos de Microsoft
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
ms.assetid: 78bd8084-ddec-4066-a474-ab5b1a0a849f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46895ff64e6585c8b80979c09874dffb510cf049
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210084"
---
# <a name="creating-the-frr-receive-location-for-receiving-from-the-back-end-application"></a>Crear la FRR ubicación de recepción para recibir de la aplicación de Back-End
Para realizar la conciliación de respuesta de FIN, debe crear una ubicación de recepción que recibe un mensaje de la aplicación de back-end en [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].  
  
 **Resumen**  
  
 Crear una ubicación de recepción con las siguientes propiedades y los componentes:  
  
|Propiedad/componente|Configuración|  
|-------------------------|-------------|  
|Puerto de recepción|Puerto unidireccional|  
|Tipo de transporte|El tipo de transporte utilizado por la aplicación back-end|  
|Dirección URI|Según sea necesario para el tipo de transporte|  
|Controlador de recepción|BizTalkServerApplication|  
|Canalización de recepción|El [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] canalización de recepción que haya creado para FRR|  
  
### <a name="to-add-an-frr-receive-location-for-receiving-from-the-back-end-application"></a>Para agregar una FRR ubicación de recepción para recibir de la aplicación de back-end  
  
1.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, **grupo de BizTalk**, **aplicaciones**, y **aplicación de BizTalk 1** nodos.  
  
2.  Haga clic en **canalizaciones**y, a continuación, haga clic en **actualizar**.  
  
3.  Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.  
  
4.  En el cuadro de diálogo Propiedades de puerto de recepción, en el **nombre** , escriba un nombre para el puerto de recepción, por ejemplo, FRRBackEndReceivePort.  
  
5.  Haga clic en **aplicar** para enlazar el puerto y, a continuación, haga clic en **Aceptar**.  
  
6.  En la consola de administración, haga clic en **ubicaciones de recepción**, seleccione **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.  
  
7.  En el, seleccione un cuadro de diálogo de puerto de recepción, seleccione el puerto de recepción recién creado y, a continuación, haga clic en **Aceptar**.  
  
8.  En el cuadro de diálogo Propiedades de la ubicación de recepción, en el **nombre** , escriba un nombre para la ubicación de recepción.  
  
9. En el **transporte** sección, para la **tipo** cuadro de texto, seleccione el tipo de transporte utilizado por la aplicación de back-end.  
  
10. Haga clic en **configurar**.  
  
11. En el cuadro de diálogo Propiedades de transporte de archivo, rellene las propiedades requeridas para el tipo de transporte y, a continuación, haga clic en **Aceptar**.  
  
12. En el cuadro de diálogo Propiedades de la ubicación de recepción, para **controlador de recepción**, seleccione **BizTalkServerApplication**.  
  
13. En el cuadro de diálogo Propiedades de la ubicación de recepción, para **canalización de recepción**, seleccione la [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] canalización de recepción que haya creado para FRR.  
  
14. Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar** para cerrar el **propiedades de la ubicación de recepción** cuadro de diálogo.  
  
15. En el Explorador de BizTalk, haga clic en la ubicación de recepción recién creado y, a continuación, haga clic en **habilitar**.