---
title: Implementar un mecanismo de liberación de lote externo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5633a448-cc29-4931-a3ad-206ae25c989b
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e88b6962cc0c83ab0ac4971f481b9ac1f185ca02
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22258140"
---
# <a name="implementing-an-external-batch-release-mechanism"></a>Implementar un mecanismo de lanzamiento de lotes externo
Puede desencadenar el lanzamiento de un lote mediante un desencadenador de versión externo. El lanzamiento se puede desencadenar de forma automática mediante una aplicación servidor, para línea empresarial al alcanzar un determinado umbral. Este mecanismo es además desencadena de forma automática el lanzamiento del lote mediante una programación o un recuento de conjuntos de transacciones o caracteres, o desencadena de forma manual el lote haciendo clic en el **invalidar** botón en el **por lotes Configuración** página de la ficha de acuerdo unidireccional.  
  
 Para implementar un desencadenador de versión externo, es necesario configurar un puerto y una ubicación de recepción para procesar OverrideControlMessage. La ubicación de recepción debe usar la canalización de recepción `Edi.BatchControlMessageRecvPipeline`. Esta es la misma canalización que usa la ubicación de recepción BatchControlMessageRecvLoc y que usa [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para procesar mensajes de invalidación de forma manual. No obstante, BatchControlMessageRecvLoc es una ubicación de recepción de tipo SQL, mientras que la ubicación de recepción que ha configurado para un desencadenador de versiones externo puede utilizar cualquier tipo de adaptador.  
  
 El mensaje de control XML desencadena un lanzamiento de lote externo. Para desencadenar el lote, la aplicación servidor enruta el mensaje de control a la ubicación de recepción. Puede modificar el mensaje de control para activar, invalidar o finalizar el lote. Vea el procedimiento que se describe a continuación para crear el mensaje de control.  
  
 Para habilitar el desencadenador de versión externo, debe seleccionar la **desencadenador de versión externo** propiedad en el **configuración de lote** página de la **propiedades del acuerdo de** cuadro de diálogo cuadro de X12 o EDIFACT. Esta propiedad indica que para la liberación de lotes es necesario un mensaje de liberación externo. El **invalidar** botón, **detener** botón, y **activación** controles de rango siguen siendo válidos si la **desencadenador de versión externo** tiene propiedad ha seleccionado.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-create-a-receive-location-for-the-external-batch-release-trigger-message"></a>Para crear una ubicación de recepción para el mensaje de desencadenador de versión de lote externo  
  
1.  En la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], cree un puerto de recepción unidireccional. Para obtener instrucciones sobre cómo crear un puerto de recepción, consulte [cómo crear un puerto de recepción](../core/how-to-create-a-receive-port.md).  
  
2.  Cree una ubicación unidireccional en el puerto de recepción.  
  
3.  Seleccione el tipo de transporte. Puede seleccionar cualquier tipo para esta ubicación de recepción. Una solución habitual es seleccionar el tipo de archivo y especificar una carpeta para recibir el archivo.  
  
4.  Para la canalización de recepción, seleccione `BatchControlMessageRecvPipeline`.  
  
5.  Haga clic en **Aceptar**.  
  
### <a name="to-create-the-external-batch-release-trigger-message"></a>Para crear el mensaje de desencadenador de versión de lote externo  
  
1.  En el Bloc de notas, cree un nuevo archivo y denomínelo con una extensión .xml.  
  
2.  Agregue lo siguiente al archivo:  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <ControlMessage xmlns="http://SQLControlMessage.IssueSelect">  
      <PAM_Control xmlns="http://SQLControlMessage.IssueSelect">  
        <DestinationParty>[Party ID]</DestinationParty>  
        <EdiMessageType>[0 for X12\HIPAA|1 for Edifact]</EdiMessageType>  
        <ActionType>EdiBatchOverride</ActionType>  
        <ActionDateTime>[yyyy-mm-ddThh:mm:ss.sss]</ActionDateTime>  
        <UsedOnce>0</UsedOnce>  
        <BatchId>[Batch ID]</BatchId>  
        <BatchName>[Batch Name]</BatchName>  
        <DestinationPartyName>[Destination Party/Partner name]</DestinationPartyName>  
        <SenderPartyName>[Sender Party/Partner name]</SenderPartyName>  
        <AgreementName>[Agreement Name]</AgreementName>  
        <ReceiverPartyNameType>[Receiver Party/Partner name]</ReceiverPartyNameType>  
        <ToBeBatched>1</ToBeBatched>  
      </PAM_Control>  
    </ControlMessage>  
    ```  
  
     Reemplace los valores del fragmento anterior, tal como se indica a continuación:  
  
    -   Especifique el tipo de acción. Normalmente, el **ActionType** debe establecerse en **EdiBatchOverride** para invalidar la configuración de lote realizada en el acuerdo. También puede establecer esto en **EdiBatchTerminate** para finalizar el lote a través de un desencadenador externo.  
  
        > [!NOTE]
        >  Microsoft recomienda no usar el desencadenador de versión externo para activar un lote. Por lo tanto, no se debe especificar **ActionType** como **EdiBatchActivate**.  
  
    -   Determine el identificador del lote y el nombre del lote. Para ello, abra el **propiedades del acuerdo de** diálogo cuadro y, en la ficha de acuerdo unidireccional, haga clic en **configuración por lotes**. Haga clic en la pestaña del lote que desea invalidar y especifique el valor de **nombre de lote** y **Updatedbatchid** campos en el **BatchName** y **BatchID**nodos del mensaje de control.  
  
    -   Especifique el nombre de la entidad de destino. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y desde el **entidades y perfiles empresariales** página, obtenga el nombre de la entidad o socio que va a recibir el por lotes intercambios. Escriba el nombre de la **ReceiverPartyNameType** nodo del mensaje de control.  
  
    -   Especifique el nombre de la entidad remitente. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y desde el **entidades y perfiles empresariales** página, obtenga el nombre de la entidad o socio que va a enviar los intercambios por lotes . Escriba el nombre de la **SenderPartyName** nodo del mensaje de control.  
  
    -   Especifique el nombre del acuerdo. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y desde el **entidades y perfiles empresariales** página, en la **contratos** sección, Haga clic en el acuerdo que tiene la configuración del lote que necesita a reemplazarse con el mensaje de control y, a continuación, haga clic en **propiedades**. En el **propiedades del acuerdo de** cuadro de diálogo la **General** ficha la **propiedades generales** página, copie el valor de la **nombre** campo en el **parámetros del acuerdo** sección y péguelo en el **AgreementName** nodo del mensaje de control.  
  
    > [!NOTE]
    >  No es necesario que especifique un identificador de entidad de destino. El elemento solo es necesario en el mensaje de control para la compatibilidad con versiones anteriores.  
  
3.  Guarde el archivo.  
  
### <a name="to-enable-the-external-release-trigger"></a>Para habilitar el desencadenador de versión externo  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y desde el **entidades y perfiles empresariales** página, en la **contratos** sección, Haga clic en el acuerdo que tiene la configuración del lote que necesita a reemplazarse con el mensaje de control y, a continuación, haga clic en **propiedades**. En el **propiedades del acuerdo de** cuadro de diálogo, en la ficha de acuerdo unidireccional, haga clic en **configuración por lotes**.  
  
2.  En el **configuración de lote** página, haga clic en la pestaña del lote para que desea tener un desencadenador de versión externo y, a continuación, en la **versión** sección, seleccione **desencadenador de versión externo** .  
  
3.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de lotes de EDI](../core/configuring-edi-batches.md)   
 [Cómo crear una ubicación de recepción](../core/how-to-create-a-receive-location.md)