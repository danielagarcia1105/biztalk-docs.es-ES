---
title: Cómo crear vínculos de rol en orquestaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc386ac2-a851-4342-9ceb-0b6faddf4ece
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e40a77392af9e97791cd9afbacc8f0b533f60288
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250428"
---
# <a name="how-to-create-role-links-in-orchestrations"></a>Cómo crear vínculos de rol en orquestaciones
Las tareas básicas que deberá realizar para usar los vínculos de rol en la orquestación son:  
  
-   Crear entidades y puertos de envío, y asociarlos entre sí  
  
-   Utilice el procedimiento siguiente para crear tipos de vínculos de rol y agregar los tipos de puerto.  
  
    |Para crear un tipo de vínculo de rol|  
    |--------------------------------|  
    |1.  En la ventana Vista orquestación, expanda **tipos**, haga clic en **tipos de vínculo de función**y, a continuación, haga clic en **nuevo tipo de vínculo de función**.<br />2.  Haga clic en el tipo de vínculo de rol que acaba de crear. En la ventana Propiedades, en la **identificador** , escriba `Provider_Consumer_RoleLinkType`.<br />3.  Expanda **Provider_Consumer_RoleLinkType**y, a continuación, haga clic en **Role_1**. En la ventana Propiedades, en la **identificador** , escriba `ConsumerRole`.<br />4.  Haga clic en **ConsumerRole**y, a continuación, haga clic en **Agregar tipo de puerto**. Con ello, se inicia el Asistente para tipo de puerto.<br />5.  En el **Asistente para el tipo de puerto** página, haga clic en **siguiente**.<br />6.  En el **seleccione un tipo de puerto o cree un nuevo tipo de puerto** , seleccione **crear un nuevo tipo de puerto**y, a continuación, para **nombre de tipo de puerto**, tipo `ConsumerPortType`.<br />7.  Para **patrón de comunicación**, seleccione **unidireccional**y para **restricciones de acceso**, seleccione **público: sin límite**. Haga clic en **Siguiente**.<br />8.  En el **completar el Asistente para puertos** página, haga clic en **finalizar**.<br />9. Haga clic en **Provider_Consumer_RoleLinkType**y, a continuación, haga clic en **nuevo rol**.<br />10. Haga clic en **Role_1**y, a continuación, en la ventana Propiedades, en la **identificador** , escriba `ProviderRole`.<br />11. Haga clic en **ProviderRole**y, a continuación, haga clic en **Agregar tipo de puerto**. Con ello, se inicia el Asistente para tipo de puerto.<br />12. En el **Asistente para el tipo de puerto** página, haga clic en **siguiente**.<br />13. En el **seleccione un tipo de puerto o cree un nuevo tipo de puerto** , seleccione **crear un nuevo tipo de puerto**y, a continuación, para **nombre de tipo de puerto**, tipo `ProviderPortType`.<br />14. Para **patrón de comunicación**, seleccione **unidireccional**y para **restricciones de acceso**, seleccione **público: sin límite**. Haga clic en **Siguiente**.<br />15. En el **completar el Asistente para puertos** página, haga clic en **finalizar**. **Nota:** puertos configurados colocados dentro de los vínculos de rol no conservan su información de enlace asociado.|  
  
     En el procedimiento anterior, crear un tipo de vínculo de función que contiene dos roles: ProviderRole, que recibirá y procesará mensajes del consumidor; y ConsumerRole que la orquestación usará el puerto de envío que se proporciona con el rol para enviar mensajes a la consumidor.  
  
> [!NOTE]
>  El tipo de vínculo de rol puede incluir un rol de proveedor y un rol de consumidor, además de poder incluir solo uno de ellos o uno de cada, dependiendo de las necesidades del proceso empresarial.  
  
-   Para agregar vínculos de rol a la orquestación, siga este procedimiento.  
  
    |Para crear un vínculo de rol con el Asistente para vínculo de función|  
    |---------------------------------------------------------|  
    |1.  En el cuadro de herramientas de orquestaciones, arrastre la **vínculo de función** forma a la superficie de diseño. Con ello, se inicia el Asistente para vínculo de función.<br />2.  En el **éste es el Asistente para vínculo de función** página, haga clic en **siguiente**.<br />3.  En el **nombre de vínculo de función** página, en la **nombre** , escriba `Provider_Consumer`. Haga clic en **Siguiente**.<br />4.  En el **tipo de vínculo de función** página, seleccione **utilizar un tipo de vínculo de rol existente**. En el **nombre de tipo de vínculo de función** lista desplegable, seleccione **Provider_Consumer_RoleLinkType**. Haga clic en **Siguiente**.<br />5.  En el **identificación de función** página, seleccione **ProviderRole** desde el **qué función implementará esta orquestación para recibir y procesar mensajes de socios?** lista desplegable. El asistente selecciona automáticamente **ConsumerRole** para **esta orquestación utilizará la siguiente función para enviar mensajes a los socios comerciales en los puertos dentro de la función**. Haga clic en **Siguiente**.<br />6.  En el **uso de vínculo de función** página, seleccione **enviaré el primer mensaje en función de mi socio**. Haga clic en **Finalizar**.|  
  
     En el procedimiento anterior, la función ConsumerRole se define de forma más detallada como rol de inicio. Esto significa que la orquestación enviará el primer mensaje al consumidor a través del puerto proporcionado por ConsumerRole y, a continuación, ProviderRole recibirá el mensaje que devuelve el consumidor para su posterior procesamiento.  
  
    > [!NOTE]
    >  Si hay solo un rol en el tipo de vínculo de rol, debe definir el rol en el proceso empresarial seleccionando la opción **rol de proveedor: recibiré el primer mensaje** o **rol de consumidor: enviaré el primer mensaje** en lugar de realizar el paso 5 del procedimiento anterior.  
  
-   Diseñar el proceso empresarial. Puede aprovechar los conjuntos de correlaciones para asegurarse de que un mensaje entrante coincide con la instancia correspondiente de una orquestación.  
  
-   Asociar los puertos con **enviar** y **recepción** formas. Además, haga lo siguiente:  
  
    -   Si el rol de inicio es un consumidor para enviar mensajes, establezca explícitamente la **DestinationParty** propiedad (una vez y solo una vez) en la orquestación. Para ello, establezca el valor de la **DestinationParty** en el **expresión** forma, como en el ejemplo siguiente, donde ConfirmOrder es el nombre de un vínculo de función, y PartnerName y OrganizationName son parámetros de una entidad:  
  
        ```  
        ConfirmOrder(Microsoft.XLANGs.BaseTypes.DestinationParty) = new Microsoft.XLANGs.BaseTypes.Party("PartnerName", "OrganizationName");  
        ```  
  
    -   Si el rol de inicio es un proveedor para recibir mensajes, la **DestinationParty** propiedad se inicializa automáticamente por el receptor. El **DestinationParty** se establece en el proveedor. El **SourceParty** propiedad es de solo lectura y se proporciona a través de un componente de canalización de confianza para resolver el nombre de la entidad en función del identificador de seguridad (SID) del remitente o de un certificado asociado a la entidad. El host que ejecuta el componente de canalización debe marcarse como **autenticación de confianza**. Puede obtener el valor de la **SourceParty** en el **expresión** forma mediante el código de ejemplo siguiente:  
  
        ```  
        PartyName = Buyer_Supplier(Microsoft.XLANGs.BaseTypes.SourceParty);  
        ```  
  
## <a name="examples-of-using-role-links"></a>Ejemplos de uso de vínculos de rol  
  
-   [PartyResolution (ejemplo de BizTalk Server)](../core/partyresolution-biztalk-server-sample.md)  
  
-   Descargue el ejemplo SDK "Using Role Links" de los ejemplos de código de BizTalk Server disponibles en [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).  
  
## <a name="see-also"></a>Vea también  
 [Usar vínculos de rol en orquestaciones](../core/using-role-links-in-orchestrations.md)   
 [Cómo usar la forma de vínculo de función](../core/how-to-use-the-role-link-shape.md)   
 [Cómo usar al Asistente para vínculo de función](../core/how-to-use-the-role-link-wizard.md)