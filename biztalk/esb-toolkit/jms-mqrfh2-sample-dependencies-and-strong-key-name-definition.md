---
title: Dependencias de ejemplo JMS MQRFH2 y clave segura nombrar definición | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3a5cdce-dcdf-48df-91a5-8cf2afce9255
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f3e2f76a972f851322f82f2e89b285db907d799
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976498"
---
# <a name="jms-mqrfh2-sample-dependencies-and-strong-key-name-definition"></a><span data-ttu-id="f1767-102">Definición de nombre de clave seguro y dependencias de ejemplo MQRFH2 JMS</span><span class="sxs-lookup"><span data-stu-id="f1767-102">JMS MQRFH2 Sample Dependencies and Strong Key Name Definition</span></span>
<span data-ttu-id="f1767-103">El proyecto de Visual Studio ESB. JMS. PipelineComponents depende de la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="f1767-103">The Visual Studio project ESB.JMS.PipelineComponents depends on the following folder:</span></span>  
  
-   <span data-ttu-id="f1767-104">\<Directorio de instalación de BizTalk Server\>.</span><span class="sxs-lookup"><span data-stu-id="f1767-104">\<BizTalk Server Installation Directory\>.</span></span> <span data-ttu-id="f1767-105">Esta carpeta proporciona acceso a los espacios de nombres siguientes:</span><span class="sxs-lookup"><span data-stu-id="f1767-105">This folder provides access to the following namespaces:</span></span>  
  
    -   <span data-ttu-id="f1767-106">**Microsoft::BizTalk::Message::Interop**</span><span class="sxs-lookup"><span data-stu-id="f1767-106">**Microsoft::BizTalk::Message::Interop**</span></span>  
  
    -   <span data-ttu-id="f1767-107">**Microsoft::BizTalk::Component::Interop**</span><span class="sxs-lookup"><span data-stu-id="f1767-107">**Microsoft::BizTalk::Component::Interop**</span></span>  
  
## <a name="the-strong-name-key-definition"></a><span data-ttu-id="f1767-108">La definición de clave de nombre seguro</span><span class="sxs-lookup"><span data-stu-id="f1767-108">The Strong Name Key Definition</span></span>  
 <span data-ttu-id="f1767-109">Normalmente, la definición de clave de nombre seguro se encuentra en el archivo AssemblyInfo.cpp.</span><span class="sxs-lookup"><span data-stu-id="f1767-109">Usually, the strong-name key definition resides in the AssemblyInfo.cpp file.</span></span> <span data-ttu-id="f1767-110">Sin embargo, esto podría entrar en conflicto con el archivo de manifiesto de C++ que el compilador agrega al ensamblado después de leer el archivo AssemblyInfo.cpp.</span><span class="sxs-lookup"><span data-stu-id="f1767-110">However, this would conflict with the C++ manifest file that the compiler adds to the assembly after it reads the AssemblyInfo.cpp file.</span></span> <span data-ttu-id="f1767-111">Este conflicto impediría que cualquier intento de colocar el archivo en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="f1767-111">This conflict would prevent any attempt to place the file in the global assembly cache.</span></span> <span data-ttu-id="f1767-112">En su lugar, el vinculador controla el archivo de clave de nombre seguro mediante la especificación de ubicado en el archivo de clave... /.. /.. /.. /.. /.. / Keys/Microsoft.Practices.ESB.snk.</span><span class="sxs-lookup"><span data-stu-id="f1767-112">Instead, the linker controls the strong name key file by specifying the key file located at ../../../../../../Keys/Microsoft.Practices.ESB.snk.</span></span> <span data-ttu-id="f1767-113">Para editar este valor, desplácese hasta la siguiente opción:</span><span class="sxs-lookup"><span data-stu-id="f1767-113">To edit this value, navigate to the following option setting:</span></span>  
  
 <span data-ttu-id="f1767-114">ESB. JMS. Esquemas</span><span class="sxs-lookup"><span data-stu-id="f1767-114">ESB.JMS.Schemas</span></span>  
  
 <span data-ttu-id="f1767-115">Proyecto de \-</span><span class="sxs-lookup"><span data-stu-id="f1767-115">\- Project</span></span>  
  
 <span data-ttu-id="f1767-116">\--Propiedades</span><span class="sxs-lookup"><span data-stu-id="f1767-116">\- - Properties</span></span>  
  
 <span data-ttu-id="f1767-117">\-: Propiedades de configuración</span><span class="sxs-lookup"><span data-stu-id="f1767-117">\- - - Configuration Properties</span></span>  
  
 <span data-ttu-id="f1767-118">\----Vinculador</span><span class="sxs-lookup"><span data-stu-id="f1767-118">\- - - - Linker</span></span>  
  
 <span data-ttu-id="f1767-119">\-----Avanzada</span><span class="sxs-lookup"><span data-stu-id="f1767-119">\- - - - - Advanced</span></span>  
  
 <span data-ttu-id="f1767-120">\------Archivo de clave</span><span class="sxs-lookup"><span data-stu-id="f1767-120">\- - - - - - Key File</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1767-121">Si se crea un componente de canalización de JMS, debe editar el archivo AssemblyInfo.cpp para quitar todas las referencias al archivo de clave de nombre seguro, como se describió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f1767-121">If you construct a JMS Pipeline Component, you must edit the AssemblyInfo.cpp file to remove any references to the strong-name key file, as described earlier.</span></span> <span data-ttu-id="f1767-122">Después de hacerlo, editar la **archivo de clave** opción en las propiedades avanzadas del vinculador para especificar la ruta de acceso y el nombre del archivo de clave de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="f1767-122">After you do that, edit the **Key File** option in the advanced properties of the Linker to specify the path and name of the strong-name key file.</span></span>