---
title: 'Paso 2: Configurar un puerto de envío WCF-WebHttp bidireccional | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0bcab296-7921-4df4-abcc-eea78cc827e8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f355275f9480cfa13f3a15bcc6522fbe7ec83b8c
ms.sourcegitcommit: e172dedfd00d4de3a40c8289f3a97ef65cdadd3c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2018
ms.locfileid: "22278892"
---
# <a name="step-2-configure-a-two-way-wcf-webhttp-send-port"></a><span data-ttu-id="c87ef-102">Paso 2: Configurar un puerto de envío WCF-WebHttp bidireccional</span><span class="sxs-lookup"><span data-stu-id="c87ef-102">Step 2: Configure a Two-way WCF-WebHttp Send Port</span></span>
<span data-ttu-id="c87ef-103">En este paso, configurará un bidireccional **WCF-WebHttp** puerto de envío para invocar la dirección URL de recursos REST para recuperar los retrasos en las compañías aéreas estadounidenses.</span><span class="sxs-lookup"><span data-stu-id="c87ef-103">In this step you configure a two-way **WCF-WebHttp** send port to invoke the REST resource URL to retrieve delays in the US air carriers’ schedules.</span></span>  
  
### <a name="to-configure-wcf-webhttp-send-port"></a><span data-ttu-id="c87ef-104">Para configurar un puerto de envío WCF-WebHttp</span><span class="sxs-lookup"><span data-stu-id="c87ef-104">To configure WCF-WebHttp send port</span></span>  
  
1.  <span data-ttu-id="c87ef-105">Desde la consola de administración de BizTalk Server, en la **BizTalk Application 1** nodo, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **estático Puerto de envío de petición-respuesta**.</span><span class="sxs-lookup"><span data-stu-id="c87ef-105">From BizTalk Server Administration Console, under the **BizTalk Application 1** node, right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
2.  <span data-ttu-id="c87ef-106">En la pestaña **General** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c87ef-106">On the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="c87ef-107">Use</span><span class="sxs-lookup"><span data-stu-id="c87ef-107">Use this</span></span>|<span data-ttu-id="c87ef-108">Para</span><span class="sxs-lookup"><span data-stu-id="c87ef-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="c87ef-109">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="c87ef-109">**Name**</span></span>|<span data-ttu-id="c87ef-110">Tipo de **SendPortRESTAzureMarketPlace**.</span><span class="sxs-lookup"><span data-stu-id="c87ef-110">Type **SendPortRESTAzureMarketPlace**.</span></span>|  
    |<span data-ttu-id="c87ef-111">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c87ef-111">**Type**</span></span>|<span data-ttu-id="c87ef-112">Seleccione **WCF-WebHttp**.</span><span class="sxs-lookup"><span data-stu-id="c87ef-112">Select **WCF-WebHttp**.</span></span>|  
    |<span data-ttu-id="c87ef-113">**Controlador de envío**</span><span class="sxs-lookup"><span data-stu-id="c87ef-113">**Send handler**</span></span>|<span data-ttu-id="c87ef-114">Seleccionar **BizTalkServerApplication**.</span><span class="sxs-lookup"><span data-stu-id="c87ef-114">Select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="c87ef-115">**Canalización de envío**</span><span class="sxs-lookup"><span data-stu-id="c87ef-115">**Send pipeline**</span></span>|<span data-ttu-id="c87ef-116">Seleccione **PassThruTransmit**.</span><span class="sxs-lookup"><span data-stu-id="c87ef-116">Select **PassThruTransmit**.</span></span>|  
    |<span data-ttu-id="c87ef-117">**La canalización de recepción**</span><span class="sxs-lookup"><span data-stu-id="c87ef-117">**Receive pipeline**</span></span>|<span data-ttu-id="c87ef-118">Seleccione **PassThruReceive**.</span><span class="sxs-lookup"><span data-stu-id="c87ef-118">Select **PassThruReceive**.</span></span>|  
  
     <span data-ttu-id="c87ef-119">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="c87ef-119">Click **Configure**.</span></span>  
  
3.  <span data-ttu-id="c87ef-120">Desde el **propiedades de transporte de WCF-WebHttp** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c87ef-120">From the **WCF-WebHttp Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="c87ef-121">En el **General** ficha, para **dirección (URI)**, escriba `https://api.datamarket.azure.com/oakleaf/US_Air_Carrier_Flight_Delays_Incr/`.</span><span class="sxs-lookup"><span data-stu-id="c87ef-121">On the **General** tab, for **Address (URI)**, enter `https://api.datamarket.azure.com/oakleaf/US_Air_Carrier_Flight_Delays_Incr/`.</span></span>  
  
    2.  <span data-ttu-id="c87ef-122">En la ficha General, para **método HTTP y asignación de dirección URL**, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c87ef-122">On the General tab, for **HTTP Method and URL Mapping**, enter the following:</span></span>  
  
        ```  
        <BtsHttpUrlMapping>  
        <Operation Method="GET" Url="/On_Time_Performance" />  
        </BtsHttpUrlMapping>  
  
        ```  
  
         <span data-ttu-id="c87ef-123">En este caso, **obtener** es el verbo HTTP y **On_Time_Performance** se anexa al URI base para construir una dirección URL de recurso único para que recupere retrasos de vuelos.</span><span class="sxs-lookup"><span data-stu-id="c87ef-123">Here, **GET** is the HTTP verb and **On_Time_Performance** is appended to the base URI to construct a unique resource URL to retrieve flight delays.</span></span>  
         
         > [!TIP] 
         > <span data-ttu-id="c87ef-124">En el campo de dirección URL, los caracteres XML especiales se deben "escape".</span><span class="sxs-lookup"><span data-stu-id="c87ef-124">Within the URL field, any special XML characters must be "escaped".</span></span> <span data-ttu-id="c87ef-125">Esto garantiza que los caracteres XML especiales se procesan y conserva el puerto.</span><span class="sxs-lookup"><span data-stu-id="c87ef-125">This ensures that the special XML characters are processed, and preserved by the port.</span></span> <span data-ttu-id="c87ef-126">Por ejemplo, el `&` caracteres especiales deben ser de escape como `&amp;`.</span><span class="sxs-lookup"><span data-stu-id="c87ef-126">For example, the `&` special character must be escaped as `&amp;`.</span></span> 
           >
           ><span data-ttu-id="c87ef-127">De:`Url=”/Customer?{ID}& group=Location”`</span><span class="sxs-lookup"><span data-stu-id="c87ef-127">From: `Url=”/Customer?{ID}& group=Location”`</span></span>
           >
           >
           ><span data-ttu-id="c87ef-128">Para:`Url=”/Customer?{ID}&amp;group=Location”`</span><span class="sxs-lookup"><span data-stu-id="c87ef-128">To: `Url=”/Customer?{ID}&amp;group=Location”`</span></span>
  
    3.  <span data-ttu-id="c87ef-129">En el **enlaces** ficha, para el **tamaño máximo de mensaje recibido** , a continuación, seleccione un valor lo suficientemente grande.</span><span class="sxs-lookup"><span data-stu-id="c87ef-129">On the **Bindings** tab, for the **Maximum Received Message Size** field, select a sufficiently large value.</span></span> <span data-ttu-id="c87ef-130">Esto se debe a que normalmente el mensaje de respuesta que contiene el estado del vuelo es considerablemente grande y puede superar el tamaño de mensaje predeterminado especificado.</span><span class="sxs-lookup"><span data-stu-id="c87ef-130">That’s because typically the response message containing the flight status is considerably large and might exceed the default message size specified.</span></span>  
  
    4.  <span data-ttu-id="c87ef-131">En el **seguridad** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c87ef-131">On the **Security** tab, do the following:</span></span>  
  
        1.  <span data-ttu-id="c87ef-132">Para el **modo de seguridad**, seleccione **transporte**.</span><span class="sxs-lookup"><span data-stu-id="c87ef-132">For the **Security mode**, select **Transport**.</span></span>  
  
        2.  <span data-ttu-id="c87ef-133">Para **tipo de credencial de cliente de transporte**, seleccione **básica**.</span><span class="sxs-lookup"><span data-stu-id="c87ef-133">For **Transport client credential type**, select **Basic**.</span></span>  
  
        3.  <span data-ttu-id="c87ef-134">En el **las credenciales de nombre de usuario** cuadro, haga clic en **editar**.</span><span class="sxs-lookup"><span data-stu-id="c87ef-134">Under the **User name credentials** box, click **Edit**.</span></span> <span data-ttu-id="c87ef-135">En el **las credenciales de cliente** cuadro de diálogo, seleccione **no utilizar inicio de sesión único en**y escriba el nombre de usuario y la contraseña que ha recuperado de la **mi cuenta** pestaña una vez haya iniciar sesión en [Windows Azure Marketplace](http://go.microsoft.com/fwlink/p/?LinkId=257913).</span><span class="sxs-lookup"><span data-stu-id="c87ef-135">In the **Client Credentials** dialog box, select **Do no use Single-Sign On**, and enter the username and password that you retrieved from the **My Account** tab after you have logged into [Windows Azure Marketplace](http://go.microsoft.com/fwlink/p/?LinkId=257913).</span></span> <span data-ttu-id="c87ef-136">Las credenciales se muestran en la **Id. de cliente** (nombre de usuario) y **clave de cuenta principal** etiquetas (contraseña).</span><span class="sxs-lookup"><span data-stu-id="c87ef-136">The credentials are listed against the **Customer ID** (user name) and **Primary Account Key** (password) labels.</span></span>  
  
        4.  <span data-ttu-id="c87ef-137">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c87ef-137">Click **OK**.</span></span>  
  
    5.  <span data-ttu-id="c87ef-138">En el **mensajes** ficha, para **suprimir el cuerpo para verbos**, especifique el verbo que desea quitar la carga del mensaje del mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="c87ef-138">On the **Messages** tab, for **Suppress Body for Verbs**, specify the verb for which you want to strip the message payload from the request message.</span></span> <span data-ttu-id="c87ef-139">Para este tutorial, especifique `GET`.</span><span class="sxs-lookup"><span data-stu-id="c87ef-139">For this tutorial, specify this as `GET`.</span></span> <span data-ttu-id="c87ef-140">Esta es la razón: una llamada de método GET en el extremo REST de US Air Carrier flight retrasos no requiere una carga de mensaje; la dirección URL de recursos REST es suficiente para recuperar la información.</span><span class="sxs-lookup"><span data-stu-id="c87ef-140">Here’s why: A GET method call on the US Air Carrier flight delays REST endpoint does not require a message payload; the REST resource URL is sufficient to retrieve the information.</span></span> <span data-ttu-id="c87ef-141">Sin embargo, para activar el **WCF-WebHttp** puerto de envío que realiza la llamada REST, se coloca un mensaje ficticio que tiene algunos cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c87ef-141">However, to trigger the **WCF-WebHttp** send port that makes the REST call, you drop a dummy message that has some message body.</span></span> <span data-ttu-id="c87ef-142">El puerto de envío no debe enviar ese mensaje ficticio al extremo REST porque, tal como se explicó anteriormente, el extremo no espera una carga de mensaje.</span><span class="sxs-lookup"><span data-stu-id="c87ef-142">The send port must not send that dummy message to the REST endpoint because, as explained earlier, the endpoint does not expect a message payload.</span></span> <span data-ttu-id="c87ef-143">Por lo tanto, antes de invocar el extremo REST, el adaptador elimina la carga del mensaje del mensaje ficticio solo para los verbos que especifique en el **suprimir el cuerpo para verbos** cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="c87ef-143">So, before invoking the REST endpoint, the adapter strips the message payload from the dummy message only for the verbs that you specify in the **Suppress Body for Verbs** text box.</span></span>  
  
    6.  <span data-ttu-id="c87ef-144">Haga clic en **Aceptar** hasta que esté en el cuadro de diálogo Propiedades de puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="c87ef-144">Click **OK** until you are back on the Send Port Properties dialog box.</span></span> <span data-ttu-id="c87ef-145">En el panel izquierdo, haga clic en **filtros**y especifique el filtro que se va a consumir todos los mensajes que se reciben a través de la recepción de puerto que ha creado en [paso 1: configurar una ubicación de recepción de archivo](../core/step-1-configure-a-file-receive-location.md).</span><span class="sxs-lookup"><span data-stu-id="c87ef-145">From the left pane, click **Filters**, and specify the filter to consume all messages that are received through the receive port you created in [Step 1: Configure a FILE Receive Location](../core/step-1-configure-a-file-receive-location.md).</span></span>  
  
        |||  
        |-|-|  
        |<span data-ttu-id="c87ef-146">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="c87ef-146">**Property**</span></span>|<span data-ttu-id="c87ef-147">Establecido en **BTS. ReceivePortName**</span><span class="sxs-lookup"><span data-stu-id="c87ef-147">Set to **BTS.ReceivePortName**</span></span>|  
        |<span data-ttu-id="c87ef-148">**Operador**</span><span class="sxs-lookup"><span data-stu-id="c87ef-148">**Operator**</span></span>|<span data-ttu-id="c87ef-149">Establecido en**==**</span><span class="sxs-lookup"><span data-stu-id="c87ef-149">Set to **==**</span></span>|  
        |<span data-ttu-id="c87ef-150">**Valor**</span><span class="sxs-lookup"><span data-stu-id="c87ef-150">**Value**</span></span>|<span data-ttu-id="c87ef-151">Establecido en`ReceivePortRestAzureMarketPlace`</span><span class="sxs-lookup"><span data-stu-id="c87ef-151">Set to `ReceivePortRestAzureMarketPlace`</span></span>|  
  
    7.  <span data-ttu-id="c87ef-152">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c87ef-152">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c87ef-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="c87ef-153">See Also</span></span>  
 [<span data-ttu-id="c87ef-154">Tutorial 5: Invocar una interfaz REST con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="c87ef-154">Tutorial 5: Invoking a REST Interface Using BizTalk Server</span></span>](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)