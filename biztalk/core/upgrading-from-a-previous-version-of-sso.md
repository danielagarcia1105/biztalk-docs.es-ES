---
title: "Actualizar desde una versión anterior de SSO | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- upgrading, SSO
- SSO, upgrading
ms.assetid: 78b99d99-9a10-4453-9db5-ae1bacd7de50
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf36c33b9480c0e8658089fdc9d996b3701d7660
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="upgrading-from-a-previous-version-of-sso"></a><span data-ttu-id="34504-102">Actualizar desde una versión anterior de SSO</span><span class="sxs-lookup"><span data-stu-id="34504-102">Upgrading from a Previous Version of SSO</span></span>
<span data-ttu-id="34504-103">Si va a instalar la característica de Enterprise Single Sign-on y ya tiene una versión anterior implementada en el equipo (por ejemplo, de Microsoft BizTalk Server 2009), debe completar los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="34504-103">If you are installing the Enterprise Single Sign-on feature and you already have a previous version deployed on your computer (for example, from Microsoft BizTalk Server 2009), you must complete the steps below.</span></span>  
  
1.  <span data-ttu-id="34504-104">Cree una copia de seguridad de la base de datos de SSO en una ubicación segura</span><span class="sxs-lookup"><span data-stu-id="34504-104">Back up the SSO database to a secure location</span></span>  
  
2.  <span data-ttu-id="34504-105">Cree una copia de seguridad de la clave secreta principal en el servidor secreto principal</span><span class="sxs-lookup"><span data-stu-id="34504-105">Back up the master secret key on the master secret server</span></span>  
  
3.  <span data-ttu-id="34504-106">Actualizar el servidor secreto principal mediante la ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] el programa de instalación, elegir **instalación personalizada**y, a continuación, seleccione **Enterprise Single Sign-On**.</span><span class="sxs-lookup"><span data-stu-id="34504-106">Update the master secret server by running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup, choosing **Custom Installation**, and then selecting **Enterprise Single Sign-On**.</span></span>  
  
4.  <span data-ttu-id="34504-107">Después de seleccionar **habilitar inicio de sesión único empresarial en este equipo**, seleccione **unir un sistema SSO existente**.</span><span class="sxs-lookup"><span data-stu-id="34504-107">After selecting **Enable Enterprise Single Sign-on on this computer**, select **Join an existing SSO system**.</span></span>  
  
 <span data-ttu-id="34504-108">No es necesario actualizar los demás servidores de SSO (servidores secretos no principales) de la instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34504-108">It is not necessary to update the other SSO servers (non-master secret servers) from your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation.</span></span> <span data-ttu-id="34504-109">Sin embargo, si desea que las nuevas características de inicio de sesión único empresarial estén disponibles en esos servidores, debe actualizarlos siguiendo el procedimiento mencionado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="34504-109">However, if you want the new Enterprise Single Sign-On features to be available on those servers, you must update them by using the same procedure outlined above.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34504-110">Estas consideraciones también se aplican si va a instalar Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un equipo con una instalación existente de Server 2009 Enterprise Single Sign-On de integración de Host y desea actualizar los servidores.</span><span class="sxs-lookup"><span data-stu-id="34504-110">These considerations also apply if you are installing Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on a computer with an existing installation of Host Integration Server 2009 Enterprise Single Sign-On, and you want to update the servers.</span></span>  
  
 <span data-ttu-id="34504-111">Si va a instalar Host Integration Server en un equipo en el que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ya esté instalado, no seleccione la característica de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="34504-111">If you are installing Host Integration Server on a computer where [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is already installed, do not select the Enterprise Single Sign-On feature.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="34504-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="34504-112">In This Section</span></span>  
  
-   [<span data-ttu-id="34504-113">Usar Host inicia la funcionalidad de SSO</span><span class="sxs-lookup"><span data-stu-id="34504-113">Using Host Initiated SSO Functionality</span></span>](../core/using-host-initiated-sso-functionality.md)  
  
-   [<span data-ttu-id="34504-114">Servidores de procesamiento de SSO</span><span class="sxs-lookup"><span data-stu-id="34504-114">Processing Servers for SSO</span></span>](../core/processing-servers-for-sso.md)