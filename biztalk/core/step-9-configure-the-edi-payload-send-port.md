---
title: 'Paso 9: Configurar el puerto de envío EDI carga | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71a8a4a7-7c3e-4e33-a9c0-a6445a3cc236
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9de1dff24af11cd03cda2550dcab921aec25d585
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277052"
---
# <a name="step-9-configure-the-edi-payload-send-port"></a>Paso 9: Configurar el puerto de envío de carga de EDI
![Paso 9 de 11](../core/media/tut-step9-of-11.gif "Tut_Step9_of_11")  
  
 En este paso, configurar un puerto de envío para enviar el XML generado a partir de la carga EDI a la aplicación de Contoso back-end, representado por la \\_EDIXMLToContoso carpeta. Este puerto de envío utiliza una canalización de envío PassThruTransmit.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-create-the-sendpayloadedixml-send-port"></a>Para crear el puerto de envío Send_Payload_EdiXml  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  
  
2.  En el **propiedades de puerto de envío** cuadro de diálogo nombre al puerto de envío **Send_Payload_EdiXml**. Seleccione **archivo** para **tipo**y, a continuación, haga clic en **configurar**.  
  
    > [!NOTE]
    >  El tipo de archivo se especifica debido a que la canalización de envío no está llevando a cabo el procesamiento AS2 en el archivo de carga. Sólo enruta el archivo de carga a una carpeta local para que pueda ver el conjunto de transacciones EDI.  
  
3.  En el **propiedades de transporte de archivo** cuadro de diálogo para **carpeta de destino**, busque y seleccione [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\_EDIXMLToContoso. Deje **nombre de archivo** como **%MessageID%.xml**. Haga clic en **Aceptar**.  
  
4.  Acepte el valor predeterminado de **PassThruTransmit** para **canalización de envío**.  
  
    > [!NOTE]
    >  Puesto que se usa la canalización de envío PassThruTransmit, la canalización no llevará a cabo ningún procesamiento EDI en el mensaje de carga, pero se enviará a la carpeta local con formato XML producido por la canalización de recepción AS2EdiReceive.  
  
5.  Haga clic en **filtros** en el árbol de consola. Para **propiedad**, escriba **BTS. MessageType**. Para **operador**, escriba  **==** . Para **valor**, escriba `http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_864`.  
  
    > [!NOTE]
    >  Este filtro garantiza que el puerto de envío sólo recogerá los mensajes de carga X12 864 del cuadro de mensajes.  
  
6.  Haga clic en **Aceptar**.  
  
7.  En el **puertos de envío** panel de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **Send_Payload_EdiXml** puerto de envío y, a continuación, haga clic en **iniciar**.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Crear un AS2 y X12 los partners de acuerdo entre los dos comerciales, como se describe en [paso 10: configurar la X12 y AS2 acuerdo de socios comerciales](../core/step-10-configure-the-x12-and-as2-trading-partner-agreement.md)  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 3: Tutorial de AS2](../core/tutorial-3-as2-tutorial.md)