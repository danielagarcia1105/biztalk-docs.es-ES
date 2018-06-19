---
title: 'Paso 7: Configurar un puerto de envío para enviar la confirmación al socio comercial | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a082870-894c-4f64-a575-3681d8a5c4ea
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59d36aaaf33673095c664363da5b3417bbd1cde4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279068"
---
# <a name="step-7-configure-a-send-port-to-send-the-acknowledgment-to-your-trading-partner"></a>Paso 7: Configurar un puerto de envío para enviar la confirmación al socio comercial
![Paso 7 de 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-7of9.gif "Step_7of9")  
  
 En este paso configura un puerto de envío para enviar el mensaje de 997 confirmación generada por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] a Fabrikam **toTHEM_997** carpeta.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-a-send-port-that-subscribes-to-the-997-acknowledgment"></a>Para configurar un puerto de envío que se suscriba a la confirmación 997  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  
  
2.  En el **propiedades de puerto de envío** diálogo cuadro, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Escriba `toTHEM_997`.|  
    |**Tipo**|Seleccione **archivo**.|  
    |**Configurar**|Haga clic en **configurar**.|  
  
    > [!NOTE]
    >  El tipo de transporte del puerto de envío es Archivo, ya que 997 es un archivo sin formato que va a enviarse a una carpeta.  
  
3.  En el **propiedades de transporte de archivo** diálogo cuadro, realice lo siguiente y, a continuación, haga clic en **Aceptar**:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Carpeta de destino**|Haga clic en **examinar**y en el **Buscar carpeta** cuadro de diálogo, desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\ escenario A\toTHEM_997.|  
    |**Nombre de archivo**|Escriba `%MessageID%.txt`y, a continuación, haga clic en **Aceptar**.|  
  
    > [!NOTE]
    >  El valor establecido para la **nombre de archivo** propiedad asegura que el archivo de salida tendrá una extensión. txt.  
  
4.  En el **propiedades de puerto de envío** cuadro de diálogo para **canalización de envío**, seleccione **EdiSend**.  
  
    > [!NOTE]
    >  La canalización de envío usada para enviar intercambios EDI, excepto para los entregados a través del transporte AS2, es la canalización EdiSend. (La canalización de envío AS2EdiSend se usa para enviar intercambios EDI entregados a través del transporte AS2).  
  
5.  En el árbol de consola, haga clic en **filtros**, y, a continuación, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Propiedad**|Seleccione **BTS. MessageType**.|  
    |**Operador**|Seleccione  **==** .|  
    |**Valor**|Escriba **http://schemas.microsoft.com/Edi/X12#X12_997_Root**.|  
  
    > [!NOTE]
    >  El filtro asegura que el puerto de envío recogerá mensajes con el tipo de mensaje 997.  
  
6.  Haga clic en **Aceptar**.  
  
7.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **puertos de envío**. Haga clic en **toTHEM_997**y, a continuación, haga clic en **iniciar** para dar de alta e iniciar el puerto.  
  
8.  En la consola de administración de BizTalk Server, en el árbol de consola, haga clic en **configuración de plataforma**y, a continuación, haga clic en **instancias de Host**. En el panel de instancias de Host, haga clic en **BizTalkServerApplication**y, a continuación, haga clic en **reiniciar**.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Crear un acuerdo entre los dos socios comerciales, como se describe en [paso 8: configurar el acuerdo de socios comerciales entre las partes](../core/step-8-configure-the-trading-partner-agreement-between-the-parties.md).  
  
## <a name="see-also"></a>Vea también  
 [Configurar un puerto de envío estático para enviar intercambios y confirmaciones EDI](../core/configuring-a-static-send-port-to-send-edi-interchanges-and-acknowledgments.md)