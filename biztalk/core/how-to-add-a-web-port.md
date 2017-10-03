---
title: "Cómo agregar un puerto Web | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web ports, creating
- creating, Web ports
ms.assetid: da94d98e-10ca-437a-ba34-7aa6efc68f3d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42e9853755788aa29d3ca7506829dcd6bdfed53d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-web-port"></a><span data-ttu-id="57192-102">Cómo agregar un puerto Web</span><span class="sxs-lookup"><span data-stu-id="57192-102">How to Add a Web Port</span></span>
<span data-ttu-id="57192-103">Los puertos Web se agregan en la superficie para el puerto en el Diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="57192-103">You add a Web port on the port surface in Orchestration Designer.</span></span> <span data-ttu-id="57192-104">A diferencia de otros puertos configurados, los puertos Web admiten una mezcla de operaciones de solicitud (unidireccionales) y de solicitud-respuesta (bidireccionales).</span><span class="sxs-lookup"><span data-stu-id="57192-104">Unlike other configured ports, Web ports support a mixture of request (one-way) and request/response (two-way) operations.</span></span> <span data-ttu-id="57192-105">Cada operación del puerto Web representa un método Web.</span><span class="sxs-lookup"><span data-stu-id="57192-105">Each operation in the Web port represents a Web method.</span></span> <span data-ttu-id="57192-106">Si el método Web contiene *entrada* y *salida* parámetros, BizTalk crea una operación de solicitud/respuesta.</span><span class="sxs-lookup"><span data-stu-id="57192-106">If the Web method contains *input* and *output* parameters, BizTalk creates a request/response operation.</span></span> <span data-ttu-id="57192-107">Si el servicio Web contiene sólo un *entrada* parámetro, BizTalk sólo crea una operación unidireccional.</span><span class="sxs-lookup"><span data-stu-id="57192-107">If the Web service contains only an *input* parameter, BizTalk only creates a one-way operation.</span></span>  
  
### <a name="to-add-a-web-port"></a><span data-ttu-id="57192-108">Para agregar un puerto Web</span><span class="sxs-lookup"><span data-stu-id="57192-108">To add a Web port</span></span>  
  
1.  <span data-ttu-id="57192-109">En el Diseñador de orquestaciones, con una orquestación abierta, haga clic en la superficie del puerto y, a continuación, seleccione **nuevo puerto configurado**.</span><span class="sxs-lookup"><span data-stu-id="57192-109">In Orchestration Designer, with an orchestration open, right-click the port surface, and then select **New Configured Port**.</span></span>  
  
2.  <span data-ttu-id="57192-110">En la página **Asistente para configuración de puertos** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="57192-110">On the **Welcome to the Port Configuration Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="57192-111">En el **propiedades de puerto** página, en la **nombre** cuadro de texto, escriba un nombre para el puerto y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="57192-111">On the **Port Properties** page, in the **Name** text box, type a name for the port, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="57192-112">En el **seleccionar un tipo de puerto** , seleccione **utilizar un tipo de puerto existente**.</span><span class="sxs-lookup"><span data-stu-id="57192-112">In the **Select a Port Type** page, select **Use an existing Port Type**.</span></span>  
  
5.  <span data-ttu-id="57192-113">En el **tipos de puertos disponibles** , expanda la **tipos de puertos Web** nodo y seleccione la Web tipo que se corresponde con el servicio Web agregado de puerto y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="57192-113">In the **Available Port Types** box, expand the **Web Port Types** node and select the Web port type that corresponds to the added Web service, and then click **Next**.</span></span>  
  
     <span data-ttu-id="57192-114">La siguiente ilustración muestra la **seleccionar un tipo de puerto** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="57192-114">The following figure shows the **Select a Port Type** dialog box.</span></span>  
  
     ![](../core/media/ebiz-prog-ws-addwebport.gif "ebiz_prog_ws_addwebport")  
  
6.  <span data-ttu-id="57192-115">En el **enlace de puerto** página, en la **enlace de puerto** lista desplegable, seleccione **especificar ahora**.</span><span class="sxs-lookup"><span data-stu-id="57192-115">In the **Port Binding** page, in the **Port binding** drop down box, select **Specify now**.</span></span> <span data-ttu-id="57192-116">BizTalk coloca automáticamente los valores desde el servicio Web al que se hace referencia en el URI, el transporte y las canalizaciones de recepción y envío.</span><span class="sxs-lookup"><span data-stu-id="57192-116">BizTalk automatically places the values from the referenced Web service in the URI, transport, and receive and send pipelines.</span></span> <span data-ttu-id="57192-117">BizTalk utiliza estos valores para crear el puerto de envío al implementar el proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="57192-117">BizTalk uses these values to create the send port when you deploy your BizTalk project.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="57192-118">El método de autenticación predeterminado para el puerto de envío es el acceso anónimo.</span><span class="sxs-lookup"><span data-stu-id="57192-118">The default authentication method for the send port is anonymous access.</span></span> <span data-ttu-id="57192-119">Si el servicio Web necesita un método de autenticación o de cifrado diferente, debe cambiar la configuración para proporcionar las credenciales de usuario adecuadas o Capa de sockets seguros (SSL) para ejecutar servicios Web.</span><span class="sxs-lookup"><span data-stu-id="57192-119">If the Web service requires a different authentication or encryption method, you must change the configuration to supply the appropriate user credentials or Secure Sockets Layer (SSL) to run Web services.</span></span> <span data-ttu-id="57192-120">Para obtener más información, consulte [: adaptador de envío SOAP](../core/soap-send-adapter.md) y [TMA de ejemplo: adaptadores SOAP y HTTP](../core/sample-tma-http-and-soap-adapters.md).</span><span class="sxs-lookup"><span data-stu-id="57192-120">For more information, see [SOAP Send Adapter](../core/soap-send-adapter.md) and [Sample TMA: HTTP and SOAP Adapters](../core/sample-tma-http-and-soap-adapters.md).</span></span>  
  
7.  <span data-ttu-id="57192-121">Haga clic en **siguiente**y, a continuación, **finalizar** para completar el asistente.</span><span class="sxs-lookup"><span data-stu-id="57192-121">Click **Next**, and then **Finish** to complete the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57192-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="57192-122">See Also</span></span>  
 <span data-ttu-id="57192-123">[Cómo ejecutar al Asistente para configuración de puertos](../core/how-to-run-the-port-configuration-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="57192-123">[How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md) </span></span>  
 [<span data-ttu-id="57192-124">Creación de puertos Web</span><span class="sxs-lookup"><span data-stu-id="57192-124">Creating Web Ports</span></span>](../core/creating-web-ports.md)