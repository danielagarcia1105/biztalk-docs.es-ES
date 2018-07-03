---
title: Cómo ampliar el Asistente del generador de esquemas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- utilities, Schema Generator Wizard
- Schema Generator Wizard
ms.assetid: ea4b5532-f904-4da0-9612-e092e7e4edc1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6fb901186dddf69a94fca4467b543f047c27719
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013813"
---
# <a name="how-to-extend-the-schema-generator-wizard"></a><span data-ttu-id="b1448-102">Cómo ampliar al Asistente del generador de esquemas</span><span class="sxs-lookup"><span data-stu-id="b1448-102">How to Extend the Schema Generator Wizard</span></span>
<span data-ttu-id="b1448-103">Cómo ampliar al Asistente del generador de esquema existentes y cómo crear a un nuevo Asistente para la generación de esquema.</span><span class="sxs-lookup"><span data-stu-id="b1448-103">How to extend the existing Schema Generator Wizard and how to create a new wizard for schema generation.</span></span>  
  
## <a name="extend-the-existing-schema-wizard"></a><span data-ttu-id="b1448-104">Ampliar al Asistente de esquemas existente</span><span class="sxs-lookup"><span data-stu-id="b1448-104">Extend the existing schema wizard</span></span>  
  
1. <span data-ttu-id="b1448-105">Implemente la interfaz ISchemaGenerator para crear un nuevo módulo de generación de esquemas que pueda integrar en el asistente del Generador de esquemas existente.</span><span class="sxs-lookup"><span data-stu-id="b1448-105">Implement the ISchemaGenerator interface to create a new schema generator module that you can integrate into the existing Schema Generator Wizard.</span></span>  
  
   ```  
   public interface ISchemaGenerator  
   {  
   //Method to extract a schema from a document.  
   void GenerateSchema(string inputDocument,string outputDocumentPath);  
  
   //Method to extract the errors.  
   [return : MarshalAs(UnmanagedType.SafeArray, SafeArraySubType = VarEnum.VT_VARIANT )]object [] Errors();  
  
   //Method to extract the warnings.  
   [return : MarshalAs(UnmanagedType.SafeArray, SafeArraySubType = VarEnum.VT_VARIANT )]object [] Warnings();  
  
   //Method to extract the referenced schemas.  
   [return : MarshalAs(UnmanagedType.SafeArray, SafeArraySubType = VarEnum.VT_VARIANT )]object [] ReferencedSchemas();  
   }  
   ```  
  
2. <span data-ttu-id="b1448-106">Coloque el ensamblado resultante en la siguiente carpeta de instalación de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="b1448-106">Drop the resulting assembly in the following Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation folder:</span></span>  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="b1448-107">Extensiones de editor \Developer Tools\Schema</span><span class="sxs-lookup"><span data-stu-id="b1448-107">\Developer Tools\Schema Editor Extensions</span></span>  
  
    <span data-ttu-id="b1448-108">La próxima vez que ejecute el asistente del Generador de esquemas, se seleccionará automáticamente el nuevo módulo de generación de esquemas.</span><span class="sxs-lookup"><span data-stu-id="b1448-108">The next time you run the Schema Generator Wizard, it will automatically pick up your new schema generator module.</span></span>  
  
   <span data-ttu-id="b1448-109">Siga el procedimiento siguiente para crear un nuevo asistente de esquemas.</span><span class="sxs-lookup"><span data-stu-id="b1448-109">Use the following procedure to create a new schema wizard.</span></span>  
  
   <span data-ttu-id="b1448-110">**Ubicación en SDK**</span><span class="sxs-lookup"><span data-stu-id="b1448-110">**Location in SDK**</span></span>  
  
   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="b1448-111">\SDK\Utilities\Schema generator</span><span class="sxs-lookup"><span data-stu-id="b1448-111">\SDK\Utilities\Schema Generator</span></span>  
  
### <a name="create-a-new-schema-wizard"></a><span data-ttu-id="b1448-112">Crear a un nuevo Asistente de esquema</span><span class="sxs-lookup"><span data-stu-id="b1448-112">Create a new schema wizard</span></span>  
  
1. <span data-ttu-id="b1448-113">Ejecute InstallDTD.vbs para instalar Microsoft.BizTalk.DTDToXSDGenerator.dll en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Developer Tools\Schema extensiones de Editor.</span><span class="sxs-lookup"><span data-stu-id="b1448-113">Run InstallDTD.vbs to install Microsoft.BizTalk.DTDToXSDGenerator.dll to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Developer Tools\Schema Editor Extensions.</span></span> <span data-ttu-id="b1448-114">DTDToXSDGenerator.dll expone las clases que puede usar para convertir archivos DTD en XSD.</span><span class="sxs-lookup"><span data-stu-id="b1448-114">DTDToXSDGenerator.dll exposes classes you can use to convert DTD files to XSD.</span></span>  
  
2. <span data-ttu-id="b1448-115">Ejecute InstallWFX.vbs para instalar Microsoft.BizTalk.WFXToXSDGenerator.dll en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Developer Tools\Schema extensiones de Editor.</span><span class="sxs-lookup"><span data-stu-id="b1448-115">Run InstallWFX.vbs to install Microsoft.BizTalk.WFXToXSDGenerator.dll to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Developer Tools\Schema Editor Extensions.</span></span> <span data-ttu-id="b1448-116">WFXToXSDGenerator.dll expone las clases que puede usar para convertir archivos WFX en XSD.</span><span class="sxs-lookup"><span data-stu-id="b1448-116">WFXToXSDGenerator.dll exposes classes you can use to convert WFX files to XSD.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1448-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1448-117">See Also</span></span>  
 [<span data-ttu-id="b1448-118">Utilidades del SDK</span><span class="sxs-lookup"><span data-stu-id="b1448-118">Utilities in the SDK</span></span>](../core/utilities-in-the-sdk.md)