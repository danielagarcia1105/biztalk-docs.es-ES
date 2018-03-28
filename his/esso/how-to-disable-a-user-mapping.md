---
title: Cómo deshabilitar una asignación de usuario | Documentos de Microsoft
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51c745dd-4d39-46e5-88bf-b803ae2e0a1b
caps.latest.revision: ''
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 93694ed8a3238be51b255bcad79122169461d885
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-disable-a-user-mapping"></a><span data-ttu-id="8758d-102">Cómo deshabilitar una asignación de usuario</span><span class="sxs-lookup"><span data-stu-id="8758d-102">How to Disable a User Mapping</span></span>
<span data-ttu-id="8758d-103">Puede deshabilitar una asignación de usuarios cuando desee desactivar todas las operaciones que están asociadas a una asignación determinada.</span><span class="sxs-lookup"><span data-stu-id="8758d-103">You can disable a user mapping when you want to turn off all operations associated with a given mapping.</span></span> <span data-ttu-id="8758d-104">Debe deshabilitar una asignación de usuarios antes de que pueda quitarla.</span><span class="sxs-lookup"><span data-stu-id="8758d-104">You must disable a user mapping before you can remove it.</span></span>  
  
 <span data-ttu-id="8758d-105">Cuando se deshabilita una asignación de usuarios, aparecerá como (D) *\<dominio >\\< nombre de usuario\>* al enumerar las asignaciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="8758d-105">When you disable a user mapping, it will appear as (D) *\<domain>\\<username\>* when you list the user mappings.</span></span>  
  
### <a name="to-disable-a-user-mapping-using-the-administration-utility"></a><span data-ttu-id="8758d-106">Para deshabilitar una asignación de usuarios con la utilidad de administración</span><span class="sxs-lookup"><span data-stu-id="8758d-106">To disable a user mapping using the administration utility</span></span>  
  
1.  <span data-ttu-id="8758d-107">Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="8758d-107">Click **Start**, click **Run**, type `cmd`, and then press **ENTER**.</span></span>  
  
2.  <span data-ttu-id="8758d-108">En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="8758d-108">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="8758d-109">El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="8758d-109">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="8758d-110">Tipo de `ssomanage –disablemapping <domain>\<username><application name>`, donde  *\<dominio >* es el dominio de Windows para la cuenta de usuario  *\<nombre de usuario >* es el nombre de usuario de Windows para el que desea deshabilitar el las credenciales, y  *\<nombre de aplicación >* es el nombre de la aplicación afiliada para la que desea quitar la asignación de usuario.</span><span class="sxs-lookup"><span data-stu-id="8758d-110">Type `ssomanage –disablemapping <domain>\<username><application name>`, where *\<domain>* is the Windows domain for the user account, *\<username>* is the Windows user name for which you want to disable the credentials, and *\<application name>* is the name of the affiliate application for which you want to remove the user mapping.</span></span>  
  
### <a name="to-disable-a-user-mapping-using-the-client-utility"></a><span data-ttu-id="8758d-111">Para deshabilitar una asignación de usuarios con la utilidad de cliente</span><span class="sxs-lookup"><span data-stu-id="8758d-111">To disable a user mapping using the client utility</span></span>  
  
1.  <span data-ttu-id="8758d-112">Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="8758d-112">Click **Start**, click **Run**, type `cmd`, and then press **ENTER**.</span></span>  
  
2.  <span data-ttu-id="8758d-113">En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="8758d-113">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="8758d-114">El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="8758d-114">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="8758d-115">Tipo de `ssoclient –disablemapping <application name>`, donde  *\<nombre de aplicación >* es el nombre de la aplicación afiliada para la que desea quitar la asignación de usuario.</span><span class="sxs-lookup"><span data-stu-id="8758d-115">Type `ssoclient –disablemapping <application name>`, where *\<application name>* is the name of the affiliate application for which you want to remove the user mapping.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8758d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="8758d-116">See Also</span></span>  
 <span data-ttu-id="8758d-117">[Asignaciones de SSO](../esso/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="8758d-117">[SSO Mappings](../esso/sso-mappings.md) </span></span>  
 <span data-ttu-id="8758d-118">[Administrar aplicaciones afiliadas](../esso/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="8758d-118">[Managing Affiliate Applications](../esso/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="8758d-119">Administración de asignaciones de usuarios</span><span class="sxs-lookup"><span data-stu-id="8758d-119">Managing User Mappings</span></span>](../esso/managing-user-mappings.md)