---
title: Personalizar archivos de enlace | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, binding files
- binding files
- binding files, about binding files
- binding files, customizing
ms.assetid: 4714e6c2-4912-43aa-ba5a-0be06916a30a
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1534be96255084b963ed3883a1370af00f73b605
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="customizing-binding-files"></a><span data-ttu-id="80685-102">Personalizar archivos de enlace</span><span class="sxs-lookup"><span data-stu-id="80685-102">Customizing Binding Files</span></span>
<span data-ttu-id="80685-103">Los archivos de enlace son archivos XML que describen artefactos en una base de datos de administración de BizTalk y la relación entre estos artefactos.</span><span class="sxs-lookup"><span data-stu-id="80685-103">Binding files are XML files that describe artifacts in a BizTalk Management database and the relationship between these artifacts.</span></span> <span data-ttu-id="80685-104">Estos archivos resultan útiles para exportar información de configuración desde una base de datos de configuración de BizTalk e importarla después a otra base de datos de configuración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="80685-104">Binding files are useful for exporting configuration information from one BizTalk configuration database and importing this information into another BizTalk configuration database.</span></span> <span data-ttu-id="80685-105">Por ejemplo, un programador puede diseñar una solución de BizTalk y sus artefactos relacionados en un entorno de desarrollo, después puede exportar estos artefactos a un archivo de enlace para, finalmente, importarlos a un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="80685-105">For example, a developer may design a BizTalk solution and its related artifacts in a development environment, then export these artifacts to a binding file and finally, import these artifacts into a production environment.</span></span> <span data-ttu-id="80685-106">También puede usar un archivo de enlace para actualizar una configuración que ya existe.</span><span class="sxs-lookup"><span data-stu-id="80685-106">You can also use a binding file to update an existing configuration.</span></span> <span data-ttu-id="80685-107">Por ejemplo, puede aplicar cambios de configuración realizados en un entorno de desarrollo al entorno de producción mediante un archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="80685-107">For example you can apply configuration changes made in a development environment to your production environment with a binding file.</span></span> <span data-ttu-id="80685-108">En este tema se tratan aspectos relativos a la actualización de una configuración que ya existe mediante un archivo de enlace, la estructura de un archivo de enlace, así como las propiedades de configuración específicas de adaptador que se pueden establecer en un archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="80685-108">This topic discusses considerations when updating an existing configuration with a binding file, the structure of a binding file, and adapter specific configuration properties that can be set in a binding file.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="80685-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="80685-109">In This Section</span></span>  
  
-   [<span data-ttu-id="80685-110">Actualizar una configuración existente con un archivo de enlace</span><span class="sxs-lookup"><span data-stu-id="80685-110">Updating an Existing Configuration with a Binding File</span></span>](../core/updating-an-existing-configuration-with-a-binding-file.md)  
  
-   [<span data-ttu-id="80685-111">Estructura de un archivo de enlace</span><span class="sxs-lookup"><span data-stu-id="80685-111">Structure of a Binding File</span></span>](../core/structure-of-a-binding-file.md)  
  
-   [<span data-ttu-id="80685-112">Propiedades de configuración para los adaptadores integrados de BizTalk</span><span class="sxs-lookup"><span data-stu-id="80685-112">Configuration Properties for Integrated BizTalk Adapters</span></span>](../core/configuration-properties-for-integrated-biztalk-adapters.md)