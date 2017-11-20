---
title: Servidores de procesamiento para SSO | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, processing servers
- processing servers [SSO]
ms.assetid: 9e80a456-974a-49b3-bb64-2e4713036cfb
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 972e1a3b01394cbf63fb0c8094586d2beda73c3e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="processing-servers-for-sso"></a><span data-ttu-id="274aa-102">Servidores de procesamiento de SSO</span><span class="sxs-lookup"><span data-stu-id="274aa-102">Processing Servers for SSO</span></span>
<span data-ttu-id="274aa-103">En un entorno con varios equipos, una vez que se ha creado el servidor secreto principal y la base de datos de SSO, es posible instalar el inicio de sesión único empresarial en equipos que se agreguen posteriormente.</span><span class="sxs-lookup"><span data-stu-id="274aa-103">In a multi-computer environment, after the master secret server and SSO database have been created, you can install Enterprise Single Sign-On on subsequent computers.</span></span> <span data-ttu-id="274aa-104">Por regla general, éstos son los equipos en los que también se instala BizTalk Server o Host Integration Server.</span><span class="sxs-lookup"><span data-stu-id="274aa-104">These are typically the computers on which either BizTalk Server or Host Integration Server is installed as well.</span></span>  
  
 <span data-ttu-id="274aa-105">El proceso de instalación inicial es el mismo que en el primer equipo.</span><span class="sxs-lookup"><span data-stu-id="274aa-105">The initial installation process is the same as on the first computer.</span></span> <span data-ttu-id="274aa-106">Sin embargo, existen algunas diferencias en la configuración.</span><span class="sxs-lookup"><span data-stu-id="274aa-106">Configuration, however, becomes slightly different.</span></span> <span data-ttu-id="274aa-107">Puesto que el servidor secreto principal y la base de datos SSO ya están instalados, seleccione **unir** cuando el Asistente para configuración le pregunte, **crear un nuevo sistema SSO** o **unir un sistema existente**.</span><span class="sxs-lookup"><span data-stu-id="274aa-107">Since the master secret server and the SSO database are already in place, select **Join** when the Configuration Wizard asks, **Create a new SSO system** or **Join an existing system**.</span></span>  
  
 <span data-ttu-id="274aa-108">Tenga en cuenta que, durante la configuración, un grupo de un equipo puede unirse a una base de datos de SSO de un equipo distinto que no sea la base de datos configurada para ese grupo.</span><span class="sxs-lookup"><span data-stu-id="274aa-108">Note that it is possible during configuration for a group on one computer to join an SSO database on a different computer that is not the database configured for that group.</span></span> <span data-ttu-id="274aa-109">No obstante, aunque esto sea posible, no resulta recomendable.</span><span class="sxs-lookup"><span data-stu-id="274aa-109">While this is possible, it is not recommended.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="274aa-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="274aa-110">See Also</span></span>  
 [<span data-ttu-id="274aa-111">Actualizar desde una versión anterior de SSO</span><span class="sxs-lookup"><span data-stu-id="274aa-111">Upgrading from a Previous Version of SSO</span></span>](../core/upgrading-from-a-previous-version-of-sso.md)