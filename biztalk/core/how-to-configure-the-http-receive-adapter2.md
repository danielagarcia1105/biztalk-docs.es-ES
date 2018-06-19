---
title: Cómo configurar la recepción HTTP < adaptador 2 | Documentos de Microsoft
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
ms.assetid: dd26fd57-90d8-4ffe-b56f-8de55ecc6f68
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed6e40036308aa872a2d6ba23da8209ee9f80cfc
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014779"
---
# <a name="how-to-configure-the-http-receive-adapter"></a><span data-ttu-id="96c4e-102">Para configurar adaptador de recepción de HTTP</span><span class="sxs-lookup"><span data-stu-id="96c4e-102">How to Configure the HTTP Receive Adapter</span></span>
<span data-ttu-id="96c4e-103">El adaptador de recepción HTTP se puede usar para enviar mensajes a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="96c4e-103">You can use the HTTP receive adapter to submit messages to BizTalk Server.</span></span> <span data-ttu-id="96c4e-104">El adaptador de recepción HTTP es una extensión ISAPI de Internet Information Services (IIS) que se hospeda en el proceso IIS.</span><span class="sxs-lookup"><span data-stu-id="96c4e-104">The HTTP receive adapter is an Internet Information Services (IIS) ISAPI extension that is hosted in the IIS process.</span></span>  
  
### <a name="to-configure-the-http-receive-adapter"></a><span data-ttu-id="96c4e-105">Para configurar el adaptador de recepción HTTP</span><span class="sxs-lookup"><span data-stu-id="96c4e-105">To configure the HTTP receive adapter</span></span>  
  
1.  <span data-ttu-id="96c4e-106">Copie el HTTP (BTSHTTPReceive.dll) de adaptador de recepción de  **\<BizTalk2010 > \HttpReceive >** a la carpeta que contiene el proyecto de inicio de sesión único (SSO) (por ejemplo, **< Adapter_install > \ biztalk2010\SSO\mySSODemo**).</span><span class="sxs-lookup"><span data-stu-id="96c4e-106">Copy the HTTP receive adapter (BTSHTTPReceive.dll) from **\<BizTalk2010>\HttpReceive>** to the folder containing your Single Sign-On (SSO) project (for example, **<Adapter_install>\biztalk2010\SSO\mySSODemo**).</span></span>  
  
    1.  <span data-ttu-id="96c4e-107">Agregue una nueva extensión de servicio Web mySSODemo.</span><span class="sxs-lookup"><span data-stu-id="96c4e-107">Add a new Web service extension mySSODemo.</span></span>  
  
    2.  <span data-ttu-id="96c4e-108">Busque y copie <BizTalk_install>\HttpReceive a la carpeta que contiene su proyecto SSO, por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="96c4e-108">Browse to and copy <BizTalk_install>\HttpReceive to the folder containing your SSO project, for example,</span></span>  
  
         <span data-ttu-id="96c4e-109"><Adapter_install>\biztalk2010\SSO\mySSODemo\BTSHTTPReceive.dll.</span><span class="sxs-lookup"><span data-stu-id="96c4e-109"><Adapter_install>\biztalk2010\SSO\mySSODemo\BTSHTTPReceive.dll.</span></span>  
  
    3.  <span data-ttu-id="96c4e-110">Establecer el estado de extensión de servicio Web mySSODemo a **permitido**.</span><span class="sxs-lookup"><span data-stu-id="96c4e-110">Set status of mySSODemo Web service extension to **Allowed**.</span></span>  
  
2.  <span data-ttu-id="96c4e-111">Reinicie IIS para asegurarse de que todos los cambios entran en vigor.</span><span class="sxs-lookup"><span data-stu-id="96c4e-111">Restart IIS to ensure that all changes are in effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96c4e-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="96c4e-112">See Also</span></span>  
 [<span data-ttu-id="96c4e-113">Seguridad en el adaptador</span><span class="sxs-lookup"><span data-stu-id="96c4e-113">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)