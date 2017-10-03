---
title: "Paso 5: Configurar un puerto de recepción y ubicación de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 43fc8d12-5fde-4ddf-a7f0-770f078ba66b
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8ec436657aefaceb71207d37808936aa6eaa1a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-5-configure-a-receive-port-and-receive-location"></a>Paso 5: Configurar un puerto de recepción y ubicación de recepción
![Paso 5 de 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-5of9.gif "Step_5of9")  
  
 En este paso, configurará un puerto de recepción y una ubicación de recepción para recibir el mensaje 850 en la carpeta configurada para la entidad Fabrikam.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-a-receive-port-and-receive-location-for-receiving-the-850-message"></a>Para configurar un puerto de recepción y una ubicación de recepción para recibir el mensaje 850  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda **administración de BizTalk Server**, **grupo de BizTalk**, **aplicaciones**y, a continuación, **BizTalk Aplicación 1**. Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.  
  
2.  En el cuadro de diálogo Propiedades de puerto de recepción, en el **nombre** , escriba `ReceiveEDI_fromTHEM_A`.  
  
3.  Haga clic en **ubicaciones de recepción** en el árbol de consola y, a continuación, haga clic en **New** en el panel derecho.  
  
4.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **nombre** , escriba `fromTHEM_4010_850`.  
  
5.  Para **tipo**, seleccione **archivo**y, a continuación, haga clic en **configurar**.  
  
    > [!NOTE]
    >  El tipo de transporte de la ubicación de recepción es Archivo, ya que el mensaje de prueba es un archivo sin formato que va a enviarse a una carpeta.  
  
6.  En el **propiedades de transporte de archivo** cuadro de diálogo, haga clic en el **examinar** situado junto a la **carpeta recepción** campo. En el **Buscar carpeta** cuadro de diálogo, desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\fromTHEM y, a continuación, haga clic en **Aceptar**.  
  
7.  En el **propiedades de transporte de archivo** cuadro de diálogo, cambie el **máscara de archivo** a  **\*.txt** y haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  La máscara de archivo está establecida como *.txt, ya que el mensaje de prueba de entrada es un archivo de texto, SamplePO.txt.  
  
8.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **canalización de recepción** campo, seleccione **EdiReceive**.  
  
    > [!NOTE]
    >  La canalización de recepción usada para recibir intercambios EDI, excepto para los entregados a través del transporte AS2, es la canalización EdiReceive. (La canalización de recepción AS2EdiReceive se usa para recibir intercambios EDI entregados a través del transporte AS2).  
  
    > [!NOTE]
    >  Si EdiReceive no se encuentra en la lista desplegable para la canalización de recepción, puede que su aplicación no tenga una referencia a la aplicación EDI de BizTalk. Para agregar la referencia, vea [cómo agregar una referencia a la aplicación EDI de BizTalk Server](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).  
  
9. Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.  
  
    > [!NOTE]
    >  La cuenta que tiene privilegios de inicio de sesión para el servicio de BizTalk deben tener también permisos de acceso completo para la carpeta de recepción asociada a la ubicación de recepción fromTHEM_4010_850 ([!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\ProcessEDI_TestLocations\fromTHEM). En caso contrario, recibirá un error al intentar habilitar la ubicación de recepción. Para cambiar los permisos de acceso para la carpeta de recepción, vaya a la ficha seguridad en el **propiedades** cuadro de diálogo de esa carpeta en el Explorador de Windows.  
  
10. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **ubicaciones de recepción**, haga clic en **fromTHEM_4010_850**y, a continuación, haga clic en **habilitar**.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Configurar el puerto de envío (**toOrderSystem**) para enviar el mensaje 850 a OrderSystem, como se describe en [paso 6: configurar un puerto de envío para enviar datos a la organización](../core/step-6-configure-a-send-port-to-send-data-to-your-organization.md).  
  
## <a name="see-also"></a>Vea también  
 [Configurar un puerto para recibir mensajes y confirmaciones EDI](../core/configuring-a-port-to-receive-edi-messages-and-acknowledgments.md)