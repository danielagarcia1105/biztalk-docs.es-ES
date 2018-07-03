---
title: Crear el FRR ubicación de recepción para recibir de la aplicación de Back-End | Microsoft Docs
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
ms.openlocfilehash: 26ac72c9d122b626411e67cfc6e18f76de226415
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002861"
---
# <a name="creating-the-frr-receive-location-for-receiving-from-the-back-end-application"></a>Crear el FRR ubicación de recepción para recibir de la aplicación de Back-End
Para llevar a cabo la conciliación de respuestas de FIN, deberá crear una ubicación de recepción que recibe un mensaje de la aplicación de back-end en [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].  

 **Resumen**  

 Crear una ubicación de recepción con los componentes y las propiedades siguientes:  


| Propiedad o el componente |                                                                 Configuración                                                                 |
|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
|    Puerto de recepción    |                                                              Puerto unidireccional                                                               |
|   Tipo de transporte   |                                           El tipo de transporte utilizado por la aplicación back-end                                           |
|    Dirección URI     |                                                   Según sea necesario para el tipo de transporte                                                    |
|  Controlador de recepción   |                                                        BizTalkServerApplication                                                         |
|  Canalización de recepción  | El [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] canalización de recepción que ha creado para FRR |

### <a name="to-add-an-frr-receive-location-for-receiving-from-the-back-end-application"></a>Para agregar una ubicación de recepción FRR para recibir de la aplicación de back-end  

1. En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, **grupo de BizTalk**, **aplicaciones**, y **aplicación de BizTalk 1** nodos.  

2. Haga clic en **canalizaciones**y, a continuación, haga clic en **actualizar**.  

3. Haga clic en **puertos de recepción**, apunte a **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.  

4. En el cuadro de diálogo Propiedades de puerto de recepción, en el **nombre** , escriba un nombre para el puerto de recepción, como FRRBackEndReceivePort.  

5. Haga clic en **aplicar** para enlazar el puerto y, a continuación, haga clic en **Aceptar**.  

6. En la consola de administración, haga clic en **ubicaciones de recepción**, apunte a **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.  

7. En el, seleccione un cuadro de diálogo de puerto de recepción, seleccione el puerto de recepción que acaba de crear y, a continuación, haga clic en **Aceptar**.  

8. En el cuadro de diálogo Propiedades de ubicación de recepción, en el **nombre** , escriba un nombre para la ubicación de recepción.  

9. En el **transporte** sección, para el **tipo** cuadro de texto, seleccione el tipo de transporte utilizado por la aplicación de back-end.  

10. Haga clic en **configurar**.  

11. En el cuadro de diálogo Propiedades de transporte de archivo, rellene las propiedades necesarias para el tipo de transporte y, a continuación, haga clic en **Aceptar**.  

12. En el cuadro de diálogo Propiedades de ubicación de recepción para **controlador de recepción**, seleccione **BizTalkServerApplication**.  

13. En el cuadro de diálogo Propiedades de ubicación de recepción para **canalización de recepción**, seleccione el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] canalización de recepción que ha creado para FRR.  

14. Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar** para cerrar el **propiedades de ubicación de recepción** cuadro de diálogo.  

15. En el Explorador de BizTalk, haga clic en la ubicación de recepción recién creado y, a continuación, haga clic en **habilitar**.
