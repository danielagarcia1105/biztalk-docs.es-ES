---
title: "Protección de la página ASPX de remitente | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ASPX pages, protocol rules
- security, ASPX pages
- RNIFSend.aspx
- ASPX pages, security
- protocol rules [ASPX pages]
ms.assetid: 8214e3f5-a8e9-4d71-957d-ed0852035030
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0c5d5ec97d4d4aed862ffc1dbc0d75d0c0430d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="securing-the-sender-aspx-page"></a><span data-ttu-id="a8784-102">Protección de la página ASPX de remitente</span><span class="sxs-lookup"><span data-stu-id="a8784-102">Securing the Sender ASPX Page</span></span>
<span data-ttu-id="a8784-103">En este tema se describe cómo proteger la página RNIFSend.aspx del uso no autorizado.</span><span class="sxs-lookup"><span data-stu-id="a8784-103">This topic describes how to protect the RNIFSend.aspx page from unauthorized use.</span></span> <span data-ttu-id="a8784-104">Hay dos procedimientos que puede usar:</span><span class="sxs-lookup"><span data-stu-id="a8784-104">There are two procedures that you can use:</span></span>  
  
-   <span data-ttu-id="a8784-105">En el Administrador de Internet Information Services (IIS), proteja RNIFSend.aspx para asegurarse de que ningún servidor no autorizado utilizará la página RNIFSend.aspx para transmitir mensajes no autorizados de la red.</span><span class="sxs-lookup"><span data-stu-id="a8784-105">In Internet Information Services (IIS) Manager, secure RNIFSend.aspx to make sure that no unauthorized server will use the RNIFSend.aspx page to transmit unauthorized messages from your network.</span></span>  
  
-   <span data-ttu-id="a8784-106">Utilice Microsoft Internet Security and Acceleration (ISA) Server para crear una regla de protocolo de solicitudes HTTP salientes.</span><span class="sxs-lookup"><span data-stu-id="a8784-106">Use Microsoft Internet Security and Acceleration (ISA) Server to create a protocol rule of outgoing HTTP requests.</span></span>  
  
### <a name="to-secure-rnifsendaspx"></a><span data-ttu-id="a8784-107">Para proteger RNIFSend.aspx</span><span class="sxs-lookup"><span data-stu-id="a8784-107">To secure RNIFSend.aspx</span></span>  
  
1.  <span data-ttu-id="a8784-108">En el servidor Web que se usa para la transmisión de mensajes RNIF, haga clic en **iniciar**, seleccione **todos los programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en  **Servicios de Internet Information Server (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="a8784-108">On the Web server you use for RNIF message transmission, click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="a8784-109">En el Administrador de IIS, expanda el nodo de equipo local, **sitios Web**y, a continuación, expanda **sitio Web predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="a8784-109">In IIS Manager, expand the local computer node, expand **Web Sites**, and then expand **Default Web Site**.</span></span>  
  
3.  <span data-ttu-id="a8784-110">Haga clic en **BTARNApp**y, a continuación, en el panel derecho, haga clic en **RNIFSend.aspx**.</span><span class="sxs-lookup"><span data-stu-id="a8784-110">Click **BTARNApp**, and then in the right pane, right-click **RNIFSend.aspx**.</span></span>  
  
4.  <span data-ttu-id="a8784-111">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a8784-111">Click **Properties**.</span></span> <span data-ttu-id="a8784-112">En el **seguridad del archivo** ficha la **restricciones de nombre de dominio y dirección IP** sección, haga clic en **editar**.</span><span class="sxs-lookup"><span data-stu-id="a8784-112">On the **File Security** tab, in the **IP address and domain name restrictions** section, click **Edit**.</span></span>  
  
5.  <span data-ttu-id="a8784-113">En el cuadro de diálogo restricciones de nombre de dominio y dirección IP, haga clic en **acceso denegado**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="a8784-113">In the IP Address and Domain Name Restrictions dialog box, click **Denied Access**, and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="a8784-114">En el **conceder acceso** cuadro de diálogo Agregar todos los servidores de BizTalk, operaciones de envío.</span><span class="sxs-lookup"><span data-stu-id="a8784-114">In the **Grant Access** dialog box, add all BizTalk Servers performing send operations.</span></span> <span data-ttu-id="a8784-115">Si agrega un solo servidor, haga clic en **único equipo**.</span><span class="sxs-lookup"><span data-stu-id="a8784-115">If adding a single server, click **Single computer**.</span></span> <span data-ttu-id="a8784-116">En el **dirección IP** , escriba la dirección IP para el equipo y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8784-116">In the **IP Address** box, type the IP address for the computer, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="a8784-117">Si agrega un grupo de servidores, haga clic en **grupo de equipos**, y, a continuación, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a8784-117">If adding a group of servers, click **Group of Computers**, and then do the following:</span></span>  
  
    |<span data-ttu-id="a8784-118">Use</span><span class="sxs-lookup"><span data-stu-id="a8784-118">Use this</span></span>|<span data-ttu-id="a8784-119">Para</span><span class="sxs-lookup"><span data-stu-id="a8784-119">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="a8784-120">**Id. de red**</span><span class="sxs-lookup"><span data-stu-id="a8784-120">**Network ID**</span></span>|<span data-ttu-id="a8784-121">Tipo de la red que desea usar.</span><span class="sxs-lookup"><span data-stu-id="a8784-121">Type the network you want to use.</span></span>|  
    |<span data-ttu-id="a8784-122">**Máscara de subred**</span><span class="sxs-lookup"><span data-stu-id="a8784-122">**Subnet mask**</span></span>|<span data-ttu-id="a8784-123">Escriba la máscara de subred que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="a8784-123">Type the subnet mask you want to use.</span></span>|  
  
8.  <span data-ttu-id="a8784-124">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8784-124">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a8784-125">Si se han distribuido todas sus operaciones de envío a un host independiente que se ejecute en una instancia independiente, solamente debe agregar este equipo.</span><span class="sxs-lookup"><span data-stu-id="a8784-125">If you have separated all your send operations to a separate host running on a separate instance, then you only have to add this computer.</span></span> <span data-ttu-id="a8784-126">Puede denegar todos los demás acceso.</span><span class="sxs-lookup"><span data-stu-id="a8784-126">You can deny all others access.</span></span>  
  
9. <span data-ttu-id="a8784-127">Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.</span><span class="sxs-lookup"><span data-stu-id="a8784-127">Click **OK**, and then click **OK** again.</span></span>  
  
### <a name="to-create-a-protocol-rule-of-outgoing-http-requests"></a><span data-ttu-id="a8784-128">Para crear una regla de protocolo de solicitudes HTTP salientes</span><span class="sxs-lookup"><span data-stu-id="a8784-128">To create a protocol rule of outgoing HTTP requests</span></span>  
  
1.  <span data-ttu-id="a8784-129">En administración de ISA, haga clic en **directiva de acceso**y, a continuación, haga clic en **las reglas de protocolo**.</span><span class="sxs-lookup"><span data-stu-id="a8784-129">In ISA Management, click **Access Policy**, and then click **Protocol Rules**.</span></span>  
  
2.  <span data-ttu-id="a8784-130">Crear una nueva regla de protocolo denominada **HTTP** que usa el protocolo TCP.</span><span class="sxs-lookup"><span data-stu-id="a8784-130">Create a new protocol rule named **HTTP** that uses TCP protocol.</span></span>  
  
3.  <span data-ttu-id="a8784-131">En la página de propiedades de su HTTP nueva regla, de protocolo en el **se aplica a** ficha, seleccione **se aplica a los conjuntos de direcciones de cliente especificadas a continuación**.</span><span class="sxs-lookup"><span data-stu-id="a8784-131">In the property page of your new HTTP protocol rule, in the **Applies To** tab, select **Applies to Client address sets specified below**.</span></span> <span data-ttu-id="a8784-132">Escriba solo esas direcciones IP que desea tener acceso a la página de cliente.</span><span class="sxs-lookup"><span data-stu-id="a8784-132">Enter only those client IPs that you want to access the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8784-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8784-133">See Also</span></span>  
 [<span data-ttu-id="a8784-134">Administrar la configuración, certificados, las bases de datos y seguridad</span><span class="sxs-lookup"><span data-stu-id="a8784-134">Manage configuration, certificates, databases, and security</span></span>](manage-configuration-certificates-databases-security.md)