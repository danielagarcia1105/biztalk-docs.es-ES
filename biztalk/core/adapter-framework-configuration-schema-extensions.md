---
title: "Extensiones de esquema de configuración de marco de trabajo de adaptadores | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 27c9727f-5f97-41ee-a0b8-45d90427b0af
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0cc50bcd592e104be0ffc82573c8ad9f4227858c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-framework-configuration-schema-extensions"></a><span data-ttu-id="51ce3-102">Extensiones de esquema de configuración de marco de trabajo de adaptadores</span><span class="sxs-lookup"><span data-stu-id="51ce3-102">Adapter Framework Configuration Schema Extensions</span></span>
<span data-ttu-id="51ce3-103">El marco de trabajo de adaptadores de BizTalk admite la generación dinámica de interfaces de usuario basadas en una definición XSD.</span><span class="sxs-lookup"><span data-stu-id="51ce3-103">The BizTalk Adapter Framework supports the dynamic generation of user interfaces based on an XSD definition.</span></span> <span data-ttu-id="51ce3-104">El adaptador proporciona la XSD necesaria y el marco de trabajo de adaptadores crea una página de propiedades que permite al usuario especificar valores.</span><span class="sxs-lookup"><span data-stu-id="51ce3-104">The adapter supplies the required XSD and the Adapter Framework creates a property page that allows the user to enter values.</span></span>  
  
 <span data-ttu-id="51ce3-105">Para crear interfaces de usuario personalizadas, el marco de trabajo de adaptadores de BizTalk proporciona varias extensiones.</span><span class="sxs-lookup"><span data-stu-id="51ce3-105">To create custom user interfaces, the Adapter Framework provides several extensions.</span></span> <span data-ttu-id="51ce3-106">Para usar estas extensiones, debe importar el esquema de marco de trabajo de adaptadores (BizTalkAdapterFramework.xsd).</span><span class="sxs-lookup"><span data-stu-id="51ce3-106">To use these extensions, you must import the Adapter Framework schema (BizTalkAdapterFramework.xsd).</span></span> <span data-ttu-id="51ce3-107">Al importar el esquema, puede usar y obtener acceso a las decoraciones y tipos especializados en el esquema de configuración del adaptador.</span><span class="sxs-lookup"><span data-stu-id="51ce3-107">By importing the schema, you can access and use the decorations and specialized types in the adapter configuration schema.</span></span>  
  
 <span data-ttu-id="51ce3-108">Use las etiquetas de decoración y los tipos integrados que se describen en esta sección para personalizar la cuadrícula de propiedades para un adaptador.</span><span class="sxs-lookup"><span data-stu-id="51ce3-108">Use the decoration tags and built-in types discussed in this section to customize the property grid for an adapter.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="51ce3-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="51ce3-109">In This Section</span></span>  
  
-   [<span data-ttu-id="51ce3-110">Habilitar extensiones de configuración de marco de trabajo de adaptadores</span><span class="sxs-lookup"><span data-stu-id="51ce3-110">Enabling Adapter Framework Configuration Extensions</span></span>](../core/enabling-adapter-framework-configuration-extensions.md)  
  
-   [<span data-ttu-id="51ce3-111">Etiquetas de decoración de esquema de configuración de adaptador Framework</span><span class="sxs-lookup"><span data-stu-id="51ce3-111">Adapter Framework Configuration Schema Decoration Tags</span></span>](../core/adapter-framework-configuration-schema-decoration-tags.md)  
  
-   [<span data-ttu-id="51ce3-112">Ejemplos de esquemas de configuración personalizada para los adaptadores</span><span class="sxs-lookup"><span data-stu-id="51ce3-112">Examples of Custom Configuration Schemas for Adapters</span></span>](../core/examples-of-custom-configuration-schemas-for-adapters.md)