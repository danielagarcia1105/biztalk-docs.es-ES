---
title: Cómo actualizar un recurso | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [resources], refreshing
- refreshing resources
- resources, refreshing
ms.assetid: d6ff7c9d-8aaf-42a4-b1a3-00c05f6ac869
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bee05b9f137bbec92eccfa217084b66f1e5bf8ee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254548"
---
# <a name="how-to-refresh-a-resource"></a><span data-ttu-id="9c405-102">Cómo actualizar un recurso</span><span class="sxs-lookup"><span data-stu-id="9c405-102">How to Refresh a Resource</span></span>
<span data-ttu-id="9c405-103">En este tema se describe cómo usar la consola de administración de BizTalk Server para actualizar un artefacto de recurso.</span><span class="sxs-lookup"><span data-stu-id="9c405-103">This topic describes how to use the BizTalk Server Administration console to refresh a resource artifact.</span></span> <span data-ttu-id="9c405-104">La información del artefacto se actualiza en la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9c405-104">This updates the artifact information in the BizTalk Management database.</span></span> <span data-ttu-id="9c405-105">Otra manera de hacerlo es mediante la adición del artefacto a la aplicación mediante BTSTask [comando AddResource](../core/addresource-command.md) con la opción de sobrescritura.</span><span class="sxs-lookup"><span data-stu-id="9c405-105">Another way to do this is by adding the artifact to the application using the BTSTask [AddResource Command](../core/addresource-command.md) with the overwrite option.</span></span>  
  
 <span data-ttu-id="9c405-106">Los artefactos de recursos están incluidos en la carpeta Recursos de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="9c405-106">Resource artifacts are contained in an application's Resources folder.</span></span> <span data-ttu-id="9c405-107">Puede ser conveniente actualizar un artefacto de recurso si realiza cambios en el archivo de origen y desea reemplazar el archivo en la aplicación con el archivo actualizado.</span><span class="sxs-lookup"><span data-stu-id="9c405-107">You might want to refresh a resource artifact if you make changes to the source file and want to replace the file in the application with the updated file.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9c405-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9c405-108">Prerequisites</span></span>  
 <span data-ttu-id="9c405-109">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="9c405-109">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="9c405-110">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="9c405-110">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-refresh-a-resource-artifact"></a><span data-ttu-id="9c405-111">Para actualizar un artefacto de recurso</span><span class="sxs-lookup"><span data-stu-id="9c405-111">To refresh a resource artifact</span></span>  
  
1.  <span data-ttu-id="9c405-112">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="9c405-112">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="9c405-113">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk que contiene el artefacto de recurso para actualizar y, a continuación, expanda la aplicación que contiene el artefacto.</span><span class="sxs-lookup"><span data-stu-id="9c405-113">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the resource artifact to refresh, and then expand the application containing the artifact.</span></span>  
  
3.  <span data-ttu-id="9c405-114">Haga clic en el **recursos** carpeta, menú contextual del archivo para actualizar y, a continuación, haga clic en **modificar**.</span><span class="sxs-lookup"><span data-stu-id="9c405-114">Click the **Resources** folder, right-click the file to refresh, and then click **Modify**.</span></span>  
  
4.  <span data-ttu-id="9c405-115">En el **modificar recursos** cuadro de diálogo, seleccione el archivo que desee actualizar y, a continuación, haga clic en **actualizar**.</span><span class="sxs-lookup"><span data-stu-id="9c405-115">In the **Modify Resources** dialog box, select the file to refresh, and then click **Refresh**.</span></span>  
  
5.  <span data-ttu-id="9c405-116">Busque el archivo actualizado con el que desea reemplazar el archivo actual y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9c405-116">Browse to the updated file with which you want to replace the current file, and then click **OK**.</span></span>  
  
     <span data-ttu-id="9c405-117">El archivo actual se reemplaza por el archivo actualizado.</span><span class="sxs-lookup"><span data-stu-id="9c405-117">The current file is replaced with the updated file.</span></span> <span data-ttu-id="9c405-118">En suma, la configuración, la configuración que aparece en el **opciones** pestaña de la **modificar recursos** cuadro de diálogo se aplican al archivo actualizado.</span><span class="sxs-lookup"><span data-stu-id="9c405-118">In addition, the configuration, settings displayed on the **Options** tab of the **Modify Resources** dialog box are applied to the refreshed file.</span></span> <span data-ttu-id="9c405-119">Para obtener más información acerca de cómo cambiar esta configuración, haga clic en **ayuda** en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="9c405-119">For more information about changing these settings, click **Help** in the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c405-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c405-120">See Also</span></span>  
 <span data-ttu-id="9c405-121">[Administrar secuencias de comandos previas y posteriores al procesamiento](../core/managing-pre-and-post-processing-scripts.md) </span><span class="sxs-lookup"><span data-stu-id="9c405-121">[Managing Pre- and Post-processing Scripts](../core/managing-pre-and-post-processing-scripts.md) </span></span>  
 <span data-ttu-id="9c405-122">[Administrar ensamblados. NET, certificados y otros recursos](../core/managing-net-assemblies-certificates-and-other-resources.md) </span><span class="sxs-lookup"><span data-stu-id="9c405-122">[Managing .NET Assemblies, Certificates, and Other Resources](../core/managing-net-assemblies-certificates-and-other-resources.md) </span></span>  
 [<span data-ttu-id="9c405-123">Administración de recursos</span><span class="sxs-lookup"><span data-stu-id="9c405-123">Managing Resources</span></span>](../core/managing-resources.md)