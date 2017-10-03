---
title: "Cómo crear puertos de envío para PeopleSoft Enterprise | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating send ports
- send ports, creating
ms.assetid: 374261ce-2cb5-4193-a0a2-658f989b2c60
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b6b5caa44976aec7a4afb8e0eccf5b1f8904111
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-send-ports-for-peoplesoft-enterprise"></a><span data-ttu-id="7ba70-102">Creación de puertos de envío para PeopleSoft Enterprise</span><span class="sxs-lookup"><span data-stu-id="7ba70-102">How to Create Send Ports for PeopleSoft Enterprise</span></span>
<span data-ttu-id="7ba70-103">Siga estos pasos para crear un puerto de envío mediante la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="7ba70-103">Follow these steps to create a send port using BizTalk Server Administration Console.</span></span>  
  
## <a name="creating-a-send-port"></a><span data-ttu-id="7ba70-104">Crear un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="7ba70-104">Creating a Send Port</span></span>  
  
#### <a name="to-create-a-send-port"></a><span data-ttu-id="7ba70-105">Procedimiento para crear un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="7ba70-105">To create a send port</span></span>  
  
1.  <span data-ttu-id="7ba70-106">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el deseado aplicación.</span><span class="sxs-lookup"><span data-stu-id="7ba70-106">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="7ba70-107">Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.</span><span class="sxs-lookup"><span data-stu-id="7ba70-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="7ba70-108">En el **propiedades de puerto de envío** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7ba70-108">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="7ba70-109">Escriba un nombre para el puerto de envío, por ejemplo, `SSOSendToPeopleSoft`.</span><span class="sxs-lookup"><span data-stu-id="7ba70-109">Type a name for the send port, for example, `SSOSendToPeopleSoft`.</span></span>  
  
    2.  <span data-ttu-id="7ba70-110">Desde el **tipo** lista desplegable, seleccione **PeopleSoft**.</span><span class="sxs-lookup"><span data-stu-id="7ba70-110">From the **Type** drop-down list, select **PeopleSoft**.</span></span>  
  
    3.  <span data-ttu-id="7ba70-111">Desde el **controlador de envío** lista desplegable, seleccione el URI.</span><span class="sxs-lookup"><span data-stu-id="7ba70-111">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="7ba70-112">En la lista desplegable de canalización de envío, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span><span class="sxs-lookup"><span data-stu-id="7ba70-112">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="7ba70-113">Desde el **canalización de recepción** lista desplegable, seleccione **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span><span class="sxs-lookup"><span data-stu-id="7ba70-113">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
    6.  <span data-ttu-id="7ba70-114">Haga clic en **configurar** para configurar el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="7ba70-114">Click **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="7ba70-115">En el **propiedades de transporte de PeopleSoft** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7ba70-115">In the **PeopleSoft Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="7ba70-116">Expanda **propiedades de adaptador necesarias**y escriba **ruta de acceso de servidor de aplicación**, **JAVA_HOME**, **nombre de usuario**,  **contraseña**y el archivo Jar para la conexión en el sistema Peoplesoft.</span><span class="sxs-lookup"><span data-stu-id="7ba70-116">Expand **Adapter Required Properties**, and enter **Application Server Path**, **JAVA_HOME**, **user name**, **password**, and the Jar file for connecting into the Peoplesoft system.</span></span>  
  
         <span data-ttu-id="7ba70-117">No tiene que establecer la información de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="7ba70-117">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="7ba70-118">En la lista, seleccione la aplicación afiliada de SSO que ha creado para representar el sistema PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="7ba70-118">In the list, select the SSO affiliate application you created to represent the PeopleSoft system.</span></span>  
  
    3.  <span data-ttu-id="7ba70-119">Para **usar SSO**, seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="7ba70-119">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="7ba70-120">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7ba70-120">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="7ba70-121">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7ba70-121">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ba70-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ba70-122">See Also</span></span>  
 [<span data-ttu-id="7ba70-123">Crear controladores de envío de PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="7ba70-123">Creating PeopleSoft Send Handlers</span></span>](../core/creating-peoplesoft-send-handlers.md)