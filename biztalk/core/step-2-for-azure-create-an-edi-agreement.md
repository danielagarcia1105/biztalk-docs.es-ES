---
title: 'Paso 2 (para Azure): Crear un acuerdo de EDI | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8003697-4955-45c0-ba0b-e7c293a050a2
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc2db7361aef663c70c7227febfea5fc08dc699a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-for-azure-create-an-edi-agreement"></a>Paso 2 (para Azure): Crear un acuerdo de EDI
En este tema, creará socios con el portal de Azure BizTalk disponible como parte de la [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]. También creará un acuerdo entre los dos socios (Northwind y Contoso) para procesar el mensaje de pedido de ventas X12 enviado por Contoso a Northwind.  
  
### <a name="to-create-partners"></a>Para crear socios  
  
1.  Con su cuenta de Microsoft, inicie sesión en el portal en [http://go.microsoft.com/fwlink/p/?LinkId=235056](http://go.microsoft.com/fwlink/p/?LinkId=235056).  
  
2.  Cree un socio para Northwind. Siga los pasos de [asociados y perfiles](http://msdn.microsoft.com/library/windowsazure/hh689791) para crear un socio.  
  
    > [!IMPORTANT]
    >  Marque este socio como el socio administrado.  
  
3.  Repita estos pasos para crear un socio para Contoso. ***No*** Marque este socio como un socio administrado.  
  
### <a name="to-create-an-agreement"></a>Para crear un acuerdo  
  
1.  En la página principal del portal, haga clic en **contratos**.  
  
2.  En el **contratos** página, haga clic en el **X12** pestaña si no está ya en esa pestaña. A continuación, haga clic en **crear acuerdo**.  
  
3.  En el **nuevo acuerdo** página, escriba la siguiente información:  
  
    |||  
    |-|-|  
    |**Campo**|**Description**|  
    |Nombre|Escriba el nombre para el acuerdo. Para este tutorial, especifique el nombre como `DemoAgreement`.<br /><br /> **Nota:** es un campo obligatorio. El nombre del acuerdo debe ser exclusivo.|  
    |Description|Escriba notas o una descripción para el acuerdo.|  
    |Perfil de socio 1 (administrado)|Seleccione el socio administrado para el acuerdo. Un socio administrado es un socio que administra el proveedor de servicios, y las canalizaciones se implementan para ese socio durante la implementación de un acuerdo. Normalmente, los socios administrados por el proveedor de servicio se configuran como socio administrado, mientras que los socios empresariales no se marcan como socios administrados.<br /><br /> **Nota:** para este tutorial, es el socio administrado **Northwind**.<br /><br /> **Nota:** el perfil predeterminado se muestra en el campo perfil. Elija el perfil deseado configurado para el socio.|  
    |Perfil de socio 2|Seleccione el socio para el acuerdo (que no es un socio administrado).<br /><br /> **Nota:** el perfil predeterminado se muestra en el campo perfil. Elija el perfil deseado configurado para el socio.|  
  
     **Identidades**  
  
    |**Campo**|**Description**|  
    |---------------|---------------------|  
    |Calificador de Id. de socio 1|Seleccione un calificador de autenticación que proporcione identidades empresariales únicas para los socios comerciales. Para este tutorial, seleccione **ZZ-definidos mutuamente**.|  
    |Valor|Escriba `Northwind`.|  
    |Calificador de Id. de socio 2|Seleccione un calificador de autenticación que proporcione identidades empresariales únicas para los socios comerciales. Para este tutorial, seleccione **ZZ-definidos mutuamente**.|  
    |Valor|Escriba `Contoso`.|  
  
     **Seguimiento**  
  
    |**Campo**|**Description**|  
    |---------------|---------------------|  
    |Seguir propiedades de mensajes de envío|Active esta opción para almacenar propiedades de mensajes cuando el mensaje EDI se envía al socio. Una vez almacenadas, puede consultar estos datos haciendo clic en **seguimiento** en el panel izquierdo en el BizTalk Portal de Azure.<br /><br /> Cuando está habilitada, también puede almacenar el cuerpo del mensaje activando **hacer seguimiento de envío de cuerpo de mensaje**.|  
    |Seguir propiedades de mensajes de recepción|Active esta opción para almacenar propiedades de mensajes cuando el mensaje EDI se recibe de un socio. Una vez almacenadas, puede consultar estos datos haciendo clic en **seguimiento** en el panel izquierdo en el BizTalk Portal de Azure.<br /><br /> Cuando está habilitada, también puede almacenar el cuerpo del mensaje activando **hacer seguimiento de recepción de cuerpo de mensaje**.|  
  
4.  Haga clic en **Continuar**.  
  
     Haga clic en **continuar** agrega dos nuevas pestañas, uno para recibir la configuración y la otra para la configuración de envío. Cada pestaña es un acuerdo unidireccional entre los dos socios, uno para los mensajes de recepción y otro para los de envío.  
  
5.  Especifique los ajustes de recepción.  
  
    1.  En el **transporte** , establezca el **tipo de transporte** a HTTP.  
  
         El **extremo** campo muestra la dirección URL a la que Contoso debe enviar el X12 mensaje de pedido de ventas.  
  
    2.  En el **protocolo** página, especifique los valores siguientes.  
  
        1.  Si es necesario, especifique valores para ISA1, ISA2, ISA3 y ISA4.  
  
        2.  En **confirmaciones**, seleccione **TA1 esperada** y **997 esperado** si desea generar confirmaciones técnicas y funcionales en respuesta para recibir el Mensaje.  
  
        3.  En **esquemas**, haga clic en el **cargar** botón y cargar la **X12 esquema 840** (descargó desde [http://go.microsoft.com/fwlink/p/? LinkId = 235057](http://go.microsoft.com/fwlink/p/?LinkId=235057)) y la **SalesOrder** esquema (creado en [para crear un esquema en el proyecto EDI](../core/step-1-for-azure-create-the-edi-project.md#BKMK_CreateSchema)).  
  
             Establezca las propiedades siguientes en el **esquemas** sección.  
  
            |||  
            |-|-|  
            |Versión|00401|  
            |Tipo de transacción (ST1)|840|  
            |esquema|/X12_00401_840.xsd|  
  
    3.  En el **transformar** página, cargue la transformación que creó en [para crear una transformación en el proyecto EDI](../core/step-1-for-azure-create-the-edi-project.md#BKMK_CreateTrfm).  
  
         En **elija los mapas que desea ejecutar como parte de este contrato**, elija **/x12_00401_840.xsd** para **esquemas** y **/EDI840TOSALESORDER. TRFM** para **nombre de archivo de transformación**.  
  
    4.  En el **ruta** página, seleccione **ruta para cola de Service Bus** y proporcione la dirección relativa de la cola a la que se envía el mensaje. Para este tutorial, especifique la dirección relativa como `queueordersedi` para que sea la dirección URL completa `https://<namespace>.servicebus.appfabriclabs.com/queueordersedi`.  
  
        > [!NOTE]
        >  Este tutorial no trata el escenario en el que se envía un mensaje con error al extremo especificado en los ajustes de suspensión de mensajes. No obstante, para una correcta implementación del acuerdo, debe proporcionar un valor para esta configuración. Puede especificar un valor que no esté en blanco.  
  
6.  Especifique los ajustes de envío.  
  
    > [!NOTE]
    >  Para el escenario descrito en este tutorial, no necesita ninguna configuración de envío para el acuerdo. No obstante, un acuerdo no puede implementarse sin especificar los ajustes de envío, incluso si son valores ficticios. Además, en la **configuración de envío** ficha, no es necesario proporcionar valores ficticios para **URI entrante**, **transformar**, y **procesamiento por lotes**.  
  
    1.  En el **protocolo** página, en **esquemas**, haga clic en el **cargar** botón y cargue el esquema para el X12 mensaje 840.  
  
         Establecer el **versión** a **00401**, **tipo de transacción** a **840**, y **esquema** a  **X12_00401_840**.  
  
    2.  En el **transporte** página, especifique los extremos donde se enviarán los mensajes de respuesta o confirmaciones a los socios. Debe especificar un extremo tanto para los mensajes procesados correctamente como para los mensajes suspendidos debido a un fallo de procesamiento.  
  
7.  Haga clic en **implementar acuerdo** para implementar el acuerdo. Ahora se implementa el acuerdo en la dirección URL que se muestra en la **transporte** página de la **configuración de recepción** ficha.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 4: Crear una aplicación híbrida mediante BizTalk Server 2013](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)