---
title: Cómo cambiar el nombre de una aplicación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- naming conventions, renaming
- naming conventions, applications
- applications, renaming
ms.assetid: ae59c792-44bd-43e0-a4ae-e67bcad2e128
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4826688935bf18cd5288924d4544f484b3dcf0cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248196"
---
# <a name="how-to-change-the-name-of-an-application"></a><span data-ttu-id="a4376-102">Cómo cambiar el nombre de una aplicación</span><span class="sxs-lookup"><span data-stu-id="a4376-102">How to Change the Name of an Application</span></span>
<span data-ttu-id="a4376-103">En este tema se describe cómo usar la consola de administración de BizTalk Server para cambiar el nombre de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="a4376-103">This topic describes how to use the BizTalk Server Administration console to change the name of an application.</span></span> <span data-ttu-id="a4376-104">Es preciso que el nombre de la aplicación que usa no exista en el grupo.</span><span class="sxs-lookup"><span data-stu-id="a4376-104">The application name that you use cannot already exist in the group.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4376-105">Si ha exportado un archivo MSI de una aplicación que tiene una referencia en la aplicación a la que se ha cambiado el nombre, la referencia ya no funcionará al importar el archivo MSI.</span><span class="sxs-lookup"><span data-stu-id="a4376-105">If you have exported an .msi file for an application that has a reference to the renamed application, the reference will no longer function when you import the .msi file.</span></span> <span data-ttu-id="a4376-106">Será necesario actualizar la referencia con el nombre nuevo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a4376-106">You will need to update the reference with the new application name.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a4376-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a4376-107">Prerequisites</span></span>  
 <span data-ttu-id="a4376-108">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="a4376-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="a4376-109">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="a4376-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-change-the-name-of-an-application"></a><span data-ttu-id="a4376-110">Para cambiar el nombre de una aplicación</span><span class="sxs-lookup"><span data-stu-id="a4376-110">To change the name of an application</span></span>  
  
1.  <span data-ttu-id="a4376-111">Haga clic en **iniciar**, seleccione **programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="a4376-111">Click **Start**, point to **Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="a4376-112">En el árbol de consola, expanda **administración de BizTalk Server**, haga clic en la aplicación cuyo nombre desea cambiar y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a4376-112">In the console tree, expand  **BizTalk Server Administration**, right-click the application whose name you want to change, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="a4376-113">En el **nombre** , escriba un nombre nuevo para la aplicación y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a4376-113">In the **Name** box, type a new name for the application, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4376-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4376-114">See Also</span></span>  
 [<span data-ttu-id="a4376-115">Creación y modificación de las aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="a4376-115">Creating and Modifying BizTalk Applications</span></span>](../core/creating-and-modifying-biztalk-applications.md)