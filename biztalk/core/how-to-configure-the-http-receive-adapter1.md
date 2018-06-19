---
title: Cómo configurar la recepción HTTP < adaptador 1 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP receive adapter, configuring
- configuring HTTP receive adapter
ms.assetid: e7dbfed3-9dd8-49c9-90b6-a655d7c5446f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c18cdcad8deaa9cd76930b91e94860c99749f78
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
ms.locfileid: "25968482"
---
# <a name="how-to-configure-the-http-receive-adapter"></a><span data-ttu-id="792a1-102">Para configurar adaptador de recepción de HTTP</span><span class="sxs-lookup"><span data-stu-id="792a1-102">How to Configure the HTTP Receive Adapter</span></span>
<span data-ttu-id="792a1-103">Puede usar el adaptador de recepción HTTP para enviar mensajes a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="792a1-103">You can use the HTTP receive adapter to submit messages to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="792a1-104">El adaptador de recepción HTTP es una extensión ISAPI de Internet Information Services (IIS) que se hospeda en el proceso IIS.</span><span class="sxs-lookup"><span data-stu-id="792a1-104">The HTTP receive adapter is an Internet Information Services (IIS) ISAPI extension that is hosted in the IIS process.</span></span>  
  
### <a name="to-configure-the-http-receive-adapter"></a><span data-ttu-id="792a1-105">Para configurar el adaptador de recepción HTTP</span><span class="sxs-lookup"><span data-stu-id="792a1-105">To configure the HTTP receive adapter</span></span>  
  
1.  <span data-ttu-id="792a1-106">Copie el HTTP (BTSHTTPReceive.dll) de adaptador de recepción de  **\<BizTalk\>\HttpReceive\>**  a la carpeta que contiene el proyecto de inicio de sesión único (SSO), por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="792a1-106">Copy the HTTP receive adapter (BTSHTTPReceive.dll) from **\<BizTalk\>\HttpReceive\>** to the folder that contains your Single Sign-On (SSO) project, for example:</span></span>  
  
     <span data-ttu-id="792a1-107">**<Adapter_install>\biztalk\SSO\mySSODemo**</span><span class="sxs-lookup"><span data-stu-id="792a1-107">**<Adapter_install>\biztalk\SSO\mySSODemo**</span></span>  
  
    1.  <span data-ttu-id="792a1-108">Agregue una nueva extensión de servicio Web mySSODemo.</span><span class="sxs-lookup"><span data-stu-id="792a1-108">Add a new Web service extension mySSODemo.</span></span>  
  
    2.  <span data-ttu-id="792a1-109">Busque y copie **< BizTalk_install > \HttpReceive** a la carpeta que contiene el proyecto SSO, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="792a1-109">Locate and copy **<BizTalk_install>\HttpReceive** to the folder that contains your SSO project, for example:</span></span>  
  
         <span data-ttu-id="792a1-110">**<Adapter_install>\biztalk\SSO\mySSODemo\BTSHTTPReceive.dll.**</span><span class="sxs-lookup"><span data-stu-id="792a1-110">**<Adapter_install>\biztalk\SSO\mySSODemo\BTSHTTPReceive.dll.**</span></span>  
  
    3.  <span data-ttu-id="792a1-111">Establecer el estado de extensión de servicio Web mySSODemo a **permitido**.</span><span class="sxs-lookup"><span data-stu-id="792a1-111">Set the status of mySSODemo Web service extension to **Allowed**.</span></span>  
  
2.  <span data-ttu-id="792a1-112">Reinicie IIS para aplicar todos los cambios.</span><span class="sxs-lookup"><span data-stu-id="792a1-112">Restart IIS to apply all changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="792a1-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="792a1-113">See Also</span></span>  
 [<span data-ttu-id="792a1-114">Proteger el adaptador</span><span class="sxs-lookup"><span data-stu-id="792a1-114">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)