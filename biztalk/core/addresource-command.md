---
title: AddResource (comando) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b09bd8d-5e07-4443-b626-60401a158540
caps.latest.revision: "33"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97d2cb07bd0a05ddd1e79f4048bfe30e51e8d866
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="addresource-command"></a><span data-ttu-id="400e4-102">AddResource (comando)</span><span class="sxs-lookup"><span data-stu-id="400e4-102">AddResource Command</span></span>
<span data-ttu-id="400e4-103">Los temas de esta sección proporcionan información de referencia acerca de los parámetros del comando AddResource.</span><span class="sxs-lookup"><span data-stu-id="400e4-103">The topics in this section provide reference information about the parameters of the AddResource command.</span></span> <span data-ttu-id="400e4-104">Los parámetros que utilizan con este comando varían según el tipo de artefacto que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="400e4-104">The parameters that you use with this command vary according to the type of artifact that you want to add.</span></span> <span data-ttu-id="400e4-105">Para obtener una lista completa de tipos de artefactos, use la **ListTypes** de comandos, como se describe en [comando ListTypes](../core/listtypes-command.md).</span><span class="sxs-lookup"><span data-stu-id="400e4-105">To obtain complete lists of artifact types, use the **ListTypes** command, as described in [ListTypes Command](../core/listtypes-command.md).</span></span>  
  
 <span data-ttu-id="400e4-106">Para obtener ayuda acerca de cómo agregar un tipo de artefacto determinado, escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="400e4-106">To get help for adding a particular artifact type, type the following command:</span></span>  
  
 <span data-ttu-id="400e4-107">**BTSTask AddResource/Type:**\<*nombre de tipo*> **/?**</span><span class="sxs-lookup"><span data-stu-id="400e4-107">**BTSTask AddResource /Type:**\<*type name*> **/?**</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="400e4-108">Si el artefacto que está agregando tiene un nombre de ruta de acceso muy largo, incluido el nombre de archivo, se producirá un error en la operación de agregar el artefacto a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="400e4-108">If the artifact you are adding has a very long path name, including the file name, the operation to add the artifact to an application may fail.</span></span> <span data-ttu-id="400e4-109">Una ruta de acceso no puede superar los 260 caracteres.</span><span class="sxs-lookup"><span data-stu-id="400e4-109">A path cannot exceed 260 characters.</span></span>  
>   
>  <span data-ttu-id="400e4-110">Si se produce un error en una operación de agregación, todas las acciones realizadas durante la operación se deshacen, con excepción de los ensamblados, que no se quitan de la caché de ensamblados global cuando han sido agregados por este comando, y las entradas, que no se quitan del Registro de Windows si no se ha creado ninguna entrada.</span><span class="sxs-lookup"><span data-stu-id="400e4-110">If an add operation fails, all actions taken during the operation are rolled back, except that assemblies are not removed from the global assembly cache if they were added by this command, and entries are not removed from the Windows registry if any entries were made.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="400e4-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="400e4-111">In This Section</span></span>  
  
-   [<span data-ttu-id="400e4-112">El comando AddResource: El ensamblado de BizTalk</span><span class="sxs-lookup"><span data-stu-id="400e4-112">AddResource Command: BizTalk Assembly</span></span>](../core/addresource-command-biztalk-assembly.md)  
  
-   [<span data-ttu-id="400e4-113">El comando AddResource: Enlace de BizTalk</span><span class="sxs-lookup"><span data-stu-id="400e4-113">AddResource Command: BizTalk Binding</span></span>](../core/addresource-command-biztalk-binding.md)  
  
-   [<span data-ttu-id="400e4-114">AddResource (comando): Ensamblado de .NET</span><span class="sxs-lookup"><span data-stu-id="400e4-114">AddResource Command: .NET Assembly</span></span>](../core/addresource-command-net-assembly.md)  
  
-   [<span data-ttu-id="400e4-115">AddResource (comando): Artefacto de BAM</span><span class="sxs-lookup"><span data-stu-id="400e4-115">AddResource Command: BAM Artifact</span></span>](../core/addresource-command-bam-artifact.md)  
  
-   [<span data-ttu-id="400e4-116">AddResource (comando): certificado</span><span class="sxs-lookup"><span data-stu-id="400e4-116">AddResource Command: Certificate</span></span>](../core/addresource-command-certificate.md)  
  
-   [<span data-ttu-id="400e4-117">AddResource (comando): Componente de COM</span><span class="sxs-lookup"><span data-stu-id="400e4-117">AddResource Command: COM Component</span></span>](../core/addresource-command-com-component.md)  
  
-   [<span data-ttu-id="400e4-118">AddResource (comando): archivo</span><span class="sxs-lookup"><span data-stu-id="400e4-118">AddResource Command: File</span></span>](../core/addresource-command-file.md)  
  
-   [<span data-ttu-id="400e4-119">AddResource (comando): Secuencia de comandos de preprocesamiento</span><span class="sxs-lookup"><span data-stu-id="400e4-119">AddResource Command: Preprocessing Script</span></span>](../core/addresource-command-preprocessing-script.md)  
  
-   [<span data-ttu-id="400e4-120">El comando AddResource: Secuencias de comandos</span><span class="sxs-lookup"><span data-stu-id="400e4-120">AddResource Command: Postprocessing Script</span></span>](../core/addresource-command-postprocessing-script.md)  
  
-   [<span data-ttu-id="400e4-121">Comando AddResource: directiva</span><span class="sxs-lookup"><span data-stu-id="400e4-121">AddResource Command: Policy</span></span>](../core/addresource-command-policy.md)  
  
-   [<span data-ttu-id="400e4-122">AddResource (comando): Directorio Virtual</span><span class="sxs-lookup"><span data-stu-id="400e4-122">AddResource Command: Virtual Directory</span></span>](../core/addresource-command-virtual-directory.md)