---
title: "Paso 6: Configurar un puerto de envío para enviar datos a su organización | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 796570ca-8178-4679-9213-d67a2a189bf9
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b513725024aec755515ccac998745220ee5dfa7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-6-configure-a-send-port-to-send-data-to-your-organization"></a>Paso 6: Configurar un puerto de envío para enviar datos a su organización
![Paso 6 de 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-6of9.gif "Step_6of9")  
  
 En este paso, configurará un puerto de envío para enviar el mensaje 850 de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] a la entidad OrderSystem que representa la organización. Este puerto de envío se aplica el **Inbound4010850_to_OrderFile** mapa, transformar el mensaje de salida del formato de mensaje de entrada al formato especificado en el mapa.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-a-send-port-for-the-850-message"></a>Para configurar un puerto de envío para el mensaje 850.  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **canalizaciones**y, a continuación, haga clic en **actualizar**.  
  
    > [!NOTE]
    >  Puede que sea necesaria la actualización de la lista de canalizaciones para poder seleccionar SendOrderFilePipeline para el puerto de envío que se va a crear.  
  
2.  Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  
  
3.  En el **propiedades de puerto de envío** diálogo cuadro, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Escriba `toOrderSystem`.|  
    |**Tipo**|Seleccione **archivo**.|  
    |**Configurar**|Haga clic en **configurar**.|  
  
    > [!NOTE]
    >  El tipo de transporte del puerto de envío es Archivo ya que el mensaje de prueba es un archivo sin formato que va a enviarse a una carpeta.  
  
4.  En el **propiedades de transporte de archivo** diálogo cuadro, realice lo siguiente y, a continuación, haga clic en **Aceptar**:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Carpeta de destino**|Haga clic en **examinar**y en el **Buscar carpeta** cuadro de diálogo, desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\ escenario A\toOrderSystem|  
    |**Nombre de archivo**|Escriba `%MessageID%.txt`y, a continuación, haga clic en **Aceptar**.|  
  
    > [!NOTE]
    >  El valor establecido para la **nombre de archivo** propiedad asegura que el archivo de salida tendrá una extensión. txt.  
  
5.  En el **propiedades de puerto de envío** cuadro de diálogo para **canalización de envío**, seleccione **SendOrderFilePipeline**.  
  
    > [!NOTE]
    >  El **SendOrderFilePipeline** enviar canalización incluye un ensamblador de archivo sin formato que ensambla el archivo de salida .txt con datos asignados desde el mensaje de entrada 850. Dado que el archivo de salida es un archivo .txt, no aparecerá en el informe de estado de intercambios y confirmaciones.  
  
6.  En el árbol de consola, haga clic en **filtros**, y, a continuación, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Propiedad**|Seleccione **BTS. ReceivePortName**.|  
    |**Operador**|Seleccione  **==** .|  
    |**Valor**|Escriba `ReceiveEDI_fromTHEM_A`.|  
    |**Agrupar por**|Seleccione **y**.|  
    |**Propiedad**|En la siguiente línea, seleccione **BTS. MessageType**.|  
    |**Operador**|Seleccione **! =**.|  
    |**Valor**|Escriba `http://schemas.microsoft.com/Edi/X12#X12_997_Root`.|  
  
    > [!NOTE]
    >  El filtro asegura que el puerto de envío tomará los mensajes que se recibieron en la ubicación de recepción Receive_EDI_fromTHEM_A y que el puerto de envío no tomará las confirmaciones 997, si no únicamente los mensajes 850.  
  
7.  En el árbol de consola, haga clic en **asignaciones de salida**. En el **asignaciones de salida** panel, en la **mapa** columna, en la primera fila, seleccione **Inbound4010850_to_OrderFile**. (La entrada en el **documento de origen** columna será X12_00401_850.)  
  
    > [!NOTE]
    >  Este paso garantiza que el mensaje de salida conste solo de los datos asignados desde el mensaje de entrada según el **Inbound4010850_to_OrderFile** mapa.  
  
8.  Haga clic en **Aceptar**.  
  
9. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **puertos de envío**. Haga clic en **toOrderSystem**y, a continuación, haga clic en **iniciar** para dar de alta e iniciar el puerto.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Configurar el puerto de envío (**toTHEM_997**) para enviar el 997 confirmación de nuevo a Fabrikam, tal y como se describe en [paso 7: configurar un puerto de envío para enviar la confirmación a su socio comercial](../core/step-7-configure-a-send-port-to-send-the-acknowledgment-to-trading-partner.md).  
  
## <a name="see-also"></a>Vea también  
 [Configurar un puerto de envío estático para enviar intercambios y confirmaciones EDI](../core/configuring-a-static-send-port-to-send-edi-interchanges-and-acknowledgments.md)