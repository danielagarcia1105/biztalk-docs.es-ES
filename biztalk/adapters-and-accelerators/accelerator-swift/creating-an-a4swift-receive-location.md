---
title: Crear una A4SWIFT la ubicación de recepción | Documentos de Microsoft
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
ms.assetid: 712cf42f-8d71-47e9-b2bf-3da158b74fe4
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11c77b7b28c65c4743998f7d4c54d9c7cd48437f
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="creating-an-a4swift-receive-location"></a>Crear una A4SWIFT la ubicación de recepción
Debe crear un [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] ubicación de recepción para habilitar la recepción de mensajes de la red SWIFT mediante [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)], tal y como se muestra en la ilustración siguiente. La ubicación de recepción recibe mensajes de archivo sin formato desde una carpeta de archivo de entrada.  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-receive-location-configuration.gif "A4SWIFT_Receive_Location_Configuration")  
  
 **Resumen**  
  
 Crear y enlazar un puerto de recepción unidireccional y, a continuación, crear y habilitar una ubicación de recepción con las siguientes propiedades y los componentes:  
  
|Propiedad/componentes|Configuración|  
|--------------------------|-------------|  
|Puerto de recepción|Puerto unidireccional|  
|Tipo de transporte|FILE|  
|Dirección URI|Nombre de la carpeta que desea recibir el mensaje|  
|Máscara de archivo|\*.  *\<extensión\>*, donde \< *extensión* \> es la extensión del entrante mensaje de archivo sin formato|  
|Controlador de recepción|BizTalkServerApplication|  
|Canalización de recepción|El [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] canalización de recepción que ha creado|  
  
### <a name="to-add-the-receive-port-and-location"></a>Para agregar el puerto de recepción y ubicación  
  
1.  Iniciar **administración de BizTalk Server** consola.  
  
    > [!NOTE]
    >  La consola de administración de BizTalk Server también puede abrir desde dentro de Visual Studio, haga clic en **administración de BizTalk Server** en el **herramientas** menú.  
  
2.  En la consola de administración, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda **BizTalk Aplicación 1**.  
  
3.  Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.  
  
4.  En el cuadro de diálogo Propiedades de puerto de recepción, en el **nombre** , escriba un nombre para el puerto de recepción.  
  
5.  Haga clic en **aplicar** para enlazar el puerto y, a continuación, haga clic en **Aceptar**.  
  
6.  Haga clic en **ubicaciones de recepción**, seleccione **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.  
  
7.  En el, seleccione un cuadro de diálogo de puerto de recepción, haga clic en el puerto de recepción recién creado y, a continuación, haga clic en **Aceptar**.  
  
8.  En el cuadro de diálogo Propiedades de la ubicación de recepción, en el **nombre** , escriba un nombre para la ubicación de recepción.  
  
9. En el **transporte** sección, para la **tipo** cuadro de texto, haga clic en la lista desplegable y, a continuación, seleccione **archivo**.  
  
10. Haga clic en el **configurar** situado a la derecha de la lista desplegable de tipo.  
  
11. En el cuadro de diálogo Propiedades de transporte de archivo, haga clic en **examinar**. Desplácese a la carpeta que desea recibir el mensaje. Haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Si esta carpeta no existe, puede crearlo mediante el **crear nueva carpeta** comando.  
  
12. En el cuadro de diálogo Propiedades de transporte de archivo, en la **máscara de archivo** cuadro, escriba  **\*.\< *extensión*\>**, donde \< *extensión* \> es la extensión del entrante mensaje de archivo sin formato, como **.txt**. Haga clic en **Aceptar**.  
  
13. En el cuadro de diálogo Propiedades de la ubicación de recepción, asegúrese de que **BizTalkServerApplication** se haya especificado para la **controlador de recepción** cuadro.  
  
14. Para el **canalización de recepción** , seleccione la canalización de recepción personalizada de la lista desplegable.  
  
15. Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.  
  
16. En la consola de administración de BizTalk Server, haga clic en **ubicaciones de recepción**, haga clic en la ubicación de recepción recién creado y, a continuación, haga clic en **habilitar**.  
  
    > [!NOTE]
    >  Después de habilitar la ubicación de recepción, BizTalk sondea activamente la carpeta de archivos.