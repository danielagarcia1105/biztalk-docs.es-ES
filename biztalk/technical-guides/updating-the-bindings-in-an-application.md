---
title: Actualización de los enlaces en una aplicación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe4ee4d8-67bf-4137-94e2-8274107c8ed6
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0add0638196e992f74ab53ebda7c429c97ca3aab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996565"
---
# <a name="updating-the-bindings-in-an-application"></a><span data-ttu-id="e1442-102">Actualización de los enlaces en una aplicación</span><span class="sxs-lookup"><span data-stu-id="e1442-102">Updating the Bindings in an Application</span></span>
<span data-ttu-id="e1442-103">Al actualizar un ensamblado en una aplicación, a menudo se sobrescriben sus enlaces o bien no se puede enlazar el ensamblado, de modo que es necesario volver a configurar los enlaces de forma manual.</span><span class="sxs-lookup"><span data-stu-id="e1442-103">When you update an assembly in an application, its bindings are often overwritten or else the assembly may not be bound at all, forcing you to manually reconfigure bindings.</span></span> <span data-ttu-id="e1442-104">Para evitar esto, puede usar un archivo de enlace para actualizar la misma versión del ensamblado o actualizar un ensamblado con una versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="e1442-104">To avoid this, you can use a binding file to update the same version of the assembly or update an assembly with a newer version.</span></span>  
  
## <a name="updating-the-same-version-of-an-assembly"></a><span data-ttu-id="e1442-105">Actualización de la misma versión de un ensamblado</span><span class="sxs-lookup"><span data-stu-id="e1442-105">Updating the Same Version of an Assembly</span></span>  
 <span data-ttu-id="e1442-106">Si el ensamblado tiene puertos enlazados o puertos dinámicos en el primer momento y cambia la configuración de puerto en la consola de administración de BizTalk Server, la configuración se perderá al actualizar el ensamblado con un ensamblado que tenga el mismo número de versión.</span><span class="sxs-lookup"><span data-stu-id="e1442-106">If the assembly has early bound ports or dynamic ports, and you changed the port configuration in the BizTalk Server Administration console, the settings will be lost when you update the assembly with an assembly having the same version number.</span></span> <span data-ttu-id="e1442-107">Puede exportar un archivo de enlace para el ensamblado que se va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="e1442-107">You can export a binding file for the assembly that you are going to update.</span></span> <span data-ttu-id="e1442-108">Después de actualizar el ensamblado, puede importar el ensamblado en la aplicación y, a continuación, importar su archivo de enlace para volver a aplicar los enlaces anteriores.</span><span class="sxs-lookup"><span data-stu-id="e1442-108">After updating the assembly, you can import the assembly into the application and then import its binding file to reapply the previous bindings.</span></span>  
  
## <a name="updating-an-assembly-with-a-newer-version"></a><span data-ttu-id="e1442-109">Actualizar un ensamblado con una versión más reciente</span><span class="sxs-lookup"><span data-stu-id="e1442-109">Updating an Assembly with a Newer Version</span></span>  
 <span data-ttu-id="e1442-110">Puede actualizar la versión de un ensamblado mediante la exportación, el enlace asociado con un único ensamblado en un archivo de enlace, editar el archivo de enlace para reflejar una nueva versión de ensamblado y, a continuación, importar los enlaces del ensamblado en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e1442-110">You can update the version of an assembly by exporting the binding associated with a single assembly into a binding file, editing the binding file to reflect a new assembly version, and then importing the bindings of the assembly into the application.</span></span> <span data-ttu-id="e1442-111">Para obtener más información acerca de cómo editar un archivo de enlace, consulte [personalizar archivos de enlace](http://go.microsoft.com/fwlink/?LinkID=155000) (HYPERLINK "<http://go.microsoft.com/fwlink/?LinkID=155000>" <http://go.microsoft.com/fwlink/?LinkID=155000>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="e1442-111">For more information about editing a binding file, see [Customizing Binding Files](http://go.microsoft.com/fwlink/?LinkID=155000) ( HYPERLINK "<http://go.microsoft.com/fwlink/?LinkID=155000>" <http://go.microsoft.com/fwlink/?LinkID=155000>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>