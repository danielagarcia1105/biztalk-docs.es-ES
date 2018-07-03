---
title: Crear una aplicación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b6e325c-a86f-419d-9a27-864f4f035507
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 772ba15d357715d5ceeca3c229167a96f7ef6c60
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987549"
---
# <a name="creating-an-application"></a><span data-ttu-id="96111-102">Creación de una aplicación</span><span class="sxs-lookup"><span data-stu-id="96111-102">Creating an Application</span></span>
<span data-ttu-id="96111-103">Hay tres formas de crear una aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="96111-103">There are three ways to create a BizTalk application.</span></span> <span data-ttu-id="96111-104">También hay varias opciones para la nomenclatura, que hacen referencia a e implementar los artefactos a las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="96111-104">There are also several options for naming, referencing, and deploying artifacts to applications.</span></span>  
  
## <a name="creating-a-biztalk-application"></a><span data-ttu-id="96111-105">Creación de una aplicación de BizTalk</span><span class="sxs-lookup"><span data-stu-id="96111-105">Creating a BizTalk Application</span></span>  
 <span data-ttu-id="96111-106">Las tres formas son como sigue:</span><span class="sxs-lookup"><span data-stu-id="96111-106">The three ways are as follows:</span></span>  
  
1. <span data-ttu-id="96111-107">Crear la aplicación de BizTalk mediante el comando de nueva aplicación de la consola de administración de BizTalk Server o el comando AddApp de la herramienta de la línea de comandos BTSTask.</span><span class="sxs-lookup"><span data-stu-id="96111-107">Create the BizTalk application by using the New Application command of the BizTalk Server Administration console or the AddApp command of the BTSTask command-line tool.</span></span> <span data-ttu-id="96111-108">Para obtener más información sobre el uso de estos comandos, consulte [cómo crear una aplicación](http://go.microsoft.com/fwlink/?LinkId=155007) (http://go.microsoft.com/fwlink/?LinkId=155007).</span><span class="sxs-lookup"><span data-stu-id="96111-108">For more information about using these commands, see [How to Create an Application](http://go.microsoft.com/fwlink/?LinkId=155007) (http://go.microsoft.com/fwlink/?LinkId=155007).</span></span>  
  
2. <span data-ttu-id="96111-109">Importar un archivo .msi exportado desde otra aplicación.</span><span class="sxs-lookup"><span data-stu-id="96111-109">Import an .msi file that was exported from another application.</span></span> <span data-ttu-id="96111-110">Si la aplicación todavía no existe en el grupo actual de BizTalk, la aplicación, incluidos sus artefactos, se creará automáticamente en el grupo actual de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="96111-110">If the application does not already exist in the current BizTalk group, the application, including its artifacts, is automatically created in the current BizTalk group.</span></span> <span data-ttu-id="96111-111">Para obtener más información sobre cómo importar aplicaciones, consulte [cómo importar una aplicación de BizTalk](http://go.microsoft.com/fwlink/?LinkID=154827) (http://go.microsoft.com/fwlink/?LinkID=154827).</span><span class="sxs-lookup"><span data-stu-id="96111-111">For more information about importing applications, see [How to Import a BizTalk Application](http://go.microsoft.com/fwlink/?LinkID=154827) (http://go.microsoft.com/fwlink/?LinkID=154827).</span></span>  
  
3. <span data-ttu-id="96111-112">Implementar ensamblados de BizTalk en una aplicación de BizTalk desde Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="96111-112">Deploy BizTalk assemblies from Visual Studio into a BizTalk application.</span></span> <span data-ttu-id="96111-113">Si la aplicación especificada en las propiedades de implementación para un proyecto en Visual Studio no existe en el grupo actual de BizTalk, se crearán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="96111-113">If the application specified in the deployment properties for a project in Visual Studio does not exist in the current BizTalk group, it will be automatically created.</span></span> <span data-ttu-id="96111-114">Para obtener más información sobre cómo implementar un ensamblado desde Visual Studio, consulte [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](http://go.microsoft.com/fwlink/?LinkID=154719) (http://go.microsoft.com/fwlink/?LinkID=154719).</span><span class="sxs-lookup"><span data-stu-id="96111-114">For more information about deploying an assembly from Visual Studio, see [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](http://go.microsoft.com/fwlink/?LinkID=154719) (http://go.microsoft.com/fwlink/?LinkID=154719).</span></span>  
  
   <span data-ttu-id="96111-115">Para implementar una aplicación mediante un archivo .msi, no necesita la aplicación de destino existe, pero se creará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="96111-115">To deploy an application using an .msi file, the destination application does not need to exist, but will be automatically created.</span></span> <span data-ttu-id="96111-116">Sin embargo, para importar enlaces desde una aplicación a otra, la aplicación de destino ya debe existir.</span><span class="sxs-lookup"><span data-stu-id="96111-116">However, to import bindings from one application to another, the destination application must already exist.</span></span> <span data-ttu-id="96111-117">Si no es así, debe crearla mediante uno de los procedimientos enumerados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="96111-117">If not, you need to create it by performing one of the procedures listed above.</span></span>  
  
   <span data-ttu-id="96111-118">Para obtener más información acerca de los pasos específicos requeridos para crear una aplicación, consulte [cómo crear una aplicación](http://go.microsoft.com/fwlink/?LinkId=155007) (http://go.microsoft.com/fwlink/?LinkId=155007).</span><span class="sxs-lookup"><span data-stu-id="96111-118">For more information about the specific steps required to create an application, see [How to Create an Application](http://go.microsoft.com/fwlink/?LinkId=155007) (http://go.microsoft.com/fwlink/?LinkId=155007).</span></span>  
  
## <a name="application-options"></a><span data-ttu-id="96111-119">Opciones de la aplicación</span><span class="sxs-lookup"><span data-stu-id="96111-119">Application Options</span></span>  
 <span data-ttu-id="96111-120">Antes de crear una nueva aplicación, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="96111-120">Before creating a new application, you should do the following:</span></span>  
  
-   <span data-ttu-id="96111-121">Determinar un nombre que sea único dentro del grupo de BizTalk para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="96111-121">Determine a name that is unique within the BizTalk group for the application.</span></span>  
  
-   <span data-ttu-id="96111-122">Agregue una referencia de la nueva aplicación para cualquier aplicación que contenga los artefactos que desea volver a usar en la nueva aplicación.</span><span class="sxs-lookup"><span data-stu-id="96111-122">Add a reference from the new application to any application containing artifacts that you want to reuse in the new application.</span></span> <span data-ttu-id="96111-123">Para obtener más información acerca de las dependencias entre aplicaciones, consulte [dependencias e implementación de aplicación](http://go.microsoft.com/fwlink/?LinkId=155008) (http://go.microsoft.com/fwlink/?LinkId=155008).</span><span class="sxs-lookup"><span data-stu-id="96111-123">For more information about dependencies between applications, see [Dependencies and Application Deployment](http://go.microsoft.com/fwlink/?LinkId=155008) (http://go.microsoft.com/fwlink/?LinkId=155008).</span></span>  
  
-   <span data-ttu-id="96111-124">Determine si desea implementar algunos artefactos en aplicaciones independientes, por ejemplo, los artefactos compartidos que se deben implementar en su propia aplicación independiente.</span><span class="sxs-lookup"><span data-stu-id="96111-124">Determine whether you want to deploy some artifacts into separate applications, for example, shared artifacts that should be deployed into their own separate application.</span></span>