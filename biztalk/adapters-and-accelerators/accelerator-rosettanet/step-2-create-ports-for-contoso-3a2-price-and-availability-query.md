---
title: 'Paso 2: Creación de puertos para el precio de 3A2 de Contoso y el escenario de respuesta de la consulta de disponibilidad mediante el Explorador de BizTalk | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating ports
ms.assetid: e0b12a96-e799-47ac-8293-7de10662bdf0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64101a31b1d1ea9c7af00471c5d764a1d8cfe598
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210148"
---
# <a name="step-2-creating-ports-for-the-contoso-3a2-price-and-availability-queryresponse-scenario"></a><span data-ttu-id="31c70-102">Paso 2: Creación de puertos para el precio de 3A2 de Contoso y el escenario de la consulta/respuesta de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="31c70-102">Step 2: Creating Ports for the Contoso 3A2 Price and Availability Query/Response Scenario</span></span>
<span data-ttu-id="31c70-103">En este paso, creará puertos de envío mediante el adaptador de SQL proporcionado por el servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="31c70-103">In this step, you create send ports using the SQL adapter provided by BizTalk Server.</span></span> <span data-ttu-id="31c70-104">Usará el puerto SQL para enviar la respuesta de precio y disponibilidad 3A2 al sistema ERP de Contoso y recibirla de él.</span><span class="sxs-lookup"><span data-stu-id="31c70-104">You use the SQL port for sending and receiving the 3A2 Price and Availability response to and from the ERP system for Contoso.</span></span>  
  
### <a name="to-configure-a-send-port-using-the-sql-adapter"></a><span data-ttu-id="31c70-105">Para configurar el puerto de envío mediante el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="31c70-105">To configure a send port using the SQL adapter</span></span>  
  
1.  <span data-ttu-id="31c70-106">En Visual Studio, en el **vista** menú, haga clic en **el Explorador de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="31c70-106">In Visual Studio, on the **View** menu, click **BizTalk Explorer**.</span></span>  
  
2.  <span data-ttu-id="31c70-107">En el Explorador de BizTalk, haga clic con el botón secundario en **Puertos de envío**y en **Agregar puerto de envío**.</span><span class="sxs-lookup"><span data-stu-id="31c70-107">In BizTalk Explorer, right-click **Send Ports**, and then click **Add Send Port**.</span></span>  
  
3.  <span data-ttu-id="31c70-108">En el cuadro de diálogo Crear nuevo puerto de envío, seleccione **Puerto de petición-respuesta estático** en la lista desplegable y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="31c70-108">In the Create New Send Port dialog box, select **Static Solicit-Response Port** from the drop-down list, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="31c70-109">En el cuadro de diálogo Propiedades del puerto de envío de petición-respuesta estático, en el cuadro **Nombre** , escriba **3A2SQLReqResponseSendPort**.</span><span class="sxs-lookup"><span data-stu-id="31c70-109">In the Static Solicit-Response Send Port Properties dialog box, in the **Name** box, type **3A2SQLReqResponseSendPort**.</span></span>  
  
5.  <span data-ttu-id="31c70-110">En la ventana Propiedades en el encabezado **General** , seleccione **SQL** como el **Tipo de transporte**.</span><span class="sxs-lookup"><span data-stu-id="31c70-110">In the Properties window under the **General** heading, select **SQL** as the **Transport Type**.</span></span>  
  
6.  <span data-ttu-id="31c70-111">En el cuadro **Dirección URI** , haga clic en el botón de puntos suspensivos (**…**).</span><span class="sxs-lookup"><span data-stu-id="31c70-111">In the **Address URI** box, click the ellipsis button (**…**).</span></span>  
  
7.  <span data-ttu-id="31c70-112">En el cuadro de diálogo Propiedades de transporte SQL, haga clic en el botón de puntos suspensivos (**…**) que se encuentra junto al cuadro **Cadena de conexión** .</span><span class="sxs-lookup"><span data-stu-id="31c70-112">In the SQL Transport Properties dialog box, click the ellipsis button (**…**) next to the **Connection String** box.</span></span>  
  
8.  <span data-ttu-id="31c70-113">En el cuadro de diálogo Propiedades de vínculo de datos, en el cuadro **Seleccione o escriba un nombre de servidor** , escriba **localhost**.</span><span class="sxs-lookup"><span data-stu-id="31c70-113">In the Data Link Properties dialog box, in the **Select or enter a server name** box, type **localhost**.</span></span>  
  
9. <span data-ttu-id="31c70-114">Seleccionar **Usar seguridad integrada de Windows**.</span><span class="sxs-lookup"><span data-stu-id="31c70-114">Select **Use Windows NT Integrated security**.</span></span>  
  
10. <span data-ttu-id="31c70-115">En el cuadro **Seleccione la base de datos del servidor** , seleccione **Contoso**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="31c70-115">In the **Select the database on the server** box, select **Contoso**, and then click **OK**.</span></span>  
  
11. <span data-ttu-id="31c70-116">En el cuadro de diálogo Propiedades de transporte SQL, en el cuadro **Target Namespace de documento** , escriba **http://Contoso.com/Price**.</span><span class="sxs-lookup"><span data-stu-id="31c70-116">In the SQL Transport Properties dialog box, in the **Document Target Namespace** box, type **http://Contoso.com/Price**.</span></span>  
  
12. <span data-ttu-id="31c70-117">En el cuadro **Nombre de elemento raíz de documento de respuesta** , escriba **rootPriceResponse**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="31c70-117">In the **Response Document Root Element Name** box, type **rootPriceResponse**, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="31c70-118">En el panel de la izquierda del cuadro de diálogo Propiedades del puerto de envío de petición-respuesta estático, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="31c70-118">In the left pane of the Static Solicit-Response Send Port Properties dialog box, click **Send**.</span></span>  
  
14. <span data-ttu-id="31c70-119">En el cuadro de diálogo estático petición-respuesta enviar puerto propiedades-configuraciones-enviar-General, en la **canalización de envío** cuadro, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="31c70-119">In the Static Solicit-Response Send Port Properties-Configurations-Send-General dialog box, in the **Send Pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
15. <span data-ttu-id="31c70-120">En el cuadro **Canalización de recepción** , seleccione **Microsoft.BizTalk.DefaultPipelines.XMLReceive**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="31c70-120">In the **Receive Pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.XMLReceive**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="31c70-121">En el Explorador de BizTalk, haga clic con el botón derecho en **3A2SQLReqResponseSendPort**, y después clic en **Dar de alta**.</span><span class="sxs-lookup"><span data-stu-id="31c70-121">In BizTalk Explorer, right-click **3A2SQLReqResponseSendPort**, and then click **Enlist**.</span></span> <span data-ttu-id="31c70-122">Haga clic en nuevo con el botón derecho y haga clic en **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="31c70-122">Right-click it again, and click **Start**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31c70-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="31c70-123">See Also</span></span>  
 [<span data-ttu-id="31c70-124">Crear y modificar el proceso privado de Contoso</span><span class="sxs-lookup"><span data-stu-id="31c70-124">Creating and Modifying the Private Process for Contoso</span></span>](creating-and-modifying-the-private-process-for-contoso.md)