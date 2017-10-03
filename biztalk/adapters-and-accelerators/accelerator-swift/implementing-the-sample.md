---
title: Implementar el ejemplo | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd788fd3-b070-40d5-a3d3-ac8e5208cc47
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d2e07078f630852fc14bf8081a4bd1453a0dc7b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="implementing-the-sample"></a><span data-ttu-id="82ef5-102">Implementar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="82ef5-102">Implementing the Sample</span></span>
<span data-ttu-id="82ef5-103">Para implementar el ejemplo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="82ef5-103">To implement the sample, proceed as follows:</span></span>  
  
1.  <span data-ttu-id="82ef5-104">Crear una nueva carpeta para SWIFT esquemas (\<DocumentSchemaLocation > en la sintaxis de la utilidad).</span><span class="sxs-lookup"><span data-stu-id="82ef5-104">Create a new folder for SWIFT schemas (\<DocumentSchemaLocation> in the utility syntax).</span></span> <span data-ttu-id="82ef5-105">Todos los esquemas para los que se va a crear o modificar los formularios de InfoPath deben encontrarse en esta carpeta cuando se ejecuta la utilidad.</span><span class="sxs-lookup"><span data-stu-id="82ef5-105">All schemas for which you are going to create/modify the InfoPath forms must be located in this folder when you execute the utility.</span></span>  
  
2.  <span data-ttu-id="82ef5-106">Si va a generar los formularios de InfoPath para los mensajes de MT, a continuación, copie **SWIFT Base Types.xsd** y **Types.xsd de datos común de SWIFT** de  **\<unidad: > \Program Acelerador de BizTalk para SWIFT \<versión del módulo de mensaje > mensaje Pack\SWIFT Messages\A4SWIFT-SRG\<versión del módulo de mensaje > \Base esquemas** en la carpeta que ha creado para SWIFT esquemas.</span><span class="sxs-lookup"><span data-stu-id="82ef5-106">If you are generating InfoPath forms for MT messages then copy **SWIFT Base Types.xsd** and **SWIFT Common Data Types.xsd** from **\<drive :> \Program Files\Microsoft BizTalk Accelerator for SWIFT \<Message Pack Version> Message Pack\SWIFT Messages\A4SWIFT-SRG\<Message Pack Version>\Base Schemas** into the folder that you created for SWIFT schemas.</span></span>  
  
3.  <span data-ttu-id="82ef5-107">Copie todos los esquemas para los que va a crear los formularios de InfoPath en la carpeta que ha creado para SWIFT esquemas en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="82ef5-107">Copy all schemas for which you are going to create InfoPath forms into the folder that you created for SWIFT schemas in Step 1.</span></span>  
  
4.  <span data-ttu-id="82ef5-108">Cree o designe una carpeta que contiene el formulario de InfoPath creado los archivos de solución de plantilla (\<DestinationFolderPath > en la sintaxis de la utilidad).</span><span class="sxs-lookup"><span data-stu-id="82ef5-108">Create or designate a folder to hold the created InfoPath form template solution files (\<DestinationFolderPath> in the utility syntax).</span></span> <span data-ttu-id="82ef5-109">Si no crea la carpeta de salida, la utilidad creará la misma con la ruta de acceso y el nombre que pasa en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="82ef5-109">If you do not create the output folder, the utility will create the same with path and name that you pass on the command line.</span></span>  
  
5.  <span data-ttu-id="82ef5-110">[Opcional]-crear un archivo de texto \<NameOfFileContainingSchemaList > que enumeran los tipos de mensaje para los mensajes para los que es el formulario de InfoPath que se genere.</span><span class="sxs-lookup"><span data-stu-id="82ef5-110">[Optional]-  Create a text file \<NameOfFileContainingSchemaList> that lists the message types for messages for which the InfoPath form is to be generated.</span></span> <span data-ttu-id="82ef5-111">Por ejemplo, el tipo de mensaje puede ser MT103, MT102 etcetera. Los nombres de mensaje pueden pasarse directamente a través de la línea de comandos en lugar de crear este archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="82ef5-111">For e.g. Message Type can be MT103, MT102 etc. The Message names can directly be passed through the command line instead of creating this text file.</span></span>  
  
## <a name="syntax-of-command-usage-for-formgeneratorexe"></a><span data-ttu-id="82ef5-112">Sintaxis de uso del comando para FormGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="82ef5-112">Syntax of Command usage for FormGenerator.exe</span></span>  
  
```csharp  
FormGenerator [-b]   [-#] <TemplateFolderPath> [<TemplateFolderPath2>   
   [...<TemplateFolderPath#>]]  
 <DestinationFolderPath>     <DocumentSchemaLocation>  
   { [<SpaceSeparatedDocumentSchemaList>] |   [-f <NameOfFileContainingSchemaList>] }  
  
```  
  
 <span data-ttu-id="82ef5-113">Donde:</span><span class="sxs-lookup"><span data-stu-id="82ef5-113">Where:</span></span>  
  
-   <span data-ttu-id="82ef5-114">-b: si se especifica, se compilará forms después de su creación.</span><span class="sxs-lookup"><span data-stu-id="82ef5-114">-b: If specified, forms will be compiled after creation.</span></span>  
  
-   <span data-ttu-id="82ef5-115">TemplateFolderPath: la carpeta que contiene los archivos de plantilla utilizados para crear la solución de InfoPath</span><span class="sxs-lookup"><span data-stu-id="82ef5-115">TemplateFolderPath: the folder containing the template files used to create the InfoPath solution</span></span>  
  
-   <span data-ttu-id="82ef5-116">-#: Si se especifica, las plantillas se buscará en varias rutas de acceso de plantilla (tantos como el entero especifica número #) y en el orden especificado.</span><span class="sxs-lookup"><span data-stu-id="82ef5-116">-#: If specified, templates will be looked up in multiple template paths (as many as the integer number # specifies) and in the order specified.</span></span>  
  
-   <span data-ttu-id="82ef5-117">DestinationFolderPath: la carpeta donde se creará los formularios</span><span class="sxs-lookup"><span data-stu-id="82ef5-117">DestinationFolderPath: the folder where the forms will be created</span></span>  
  
-   <span data-ttu-id="82ef5-118">DocumentSchemaLocation: ubicación de esquemas (incluidos los esquemas de base y comunes para los mensajes de MT)</span><span class="sxs-lookup"><span data-stu-id="82ef5-118">DocumentSchemaLocation: location of schemas (including base and common schemas for MT messages)</span></span>  
  
-   <span data-ttu-id="82ef5-119">SpaceSeparatedDocumentSchemaList: lista separada por espacios de esquemas como MT103 MT300.</span><span class="sxs-lookup"><span data-stu-id="82ef5-119">SpaceSeparatedDocumentSchemaList: space-separated list of schemas like MT103 MT300.</span></span>  
  
-   <span data-ttu-id="82ef5-120">-f: si se especifica, la lista de esquemas tiene que leerse desde un archivo.</span><span class="sxs-lookup"><span data-stu-id="82ef5-120">-f: If specified, the schema list needs to be read from a file.</span></span>  
  
-   <span data-ttu-id="82ef5-121">NameOfFileContainingSchemaList: el nombre del archivo que contiene la lista.</span><span class="sxs-lookup"><span data-stu-id="82ef5-121">NameOfFileContainingSchemaList: name of file containing the list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="82ef5-122">El comando anterior es un comando genérico para MT, MX y categoría 0 mensajes.</span><span class="sxs-lookup"><span data-stu-id="82ef5-122">The above command is a generic command for MT, MX and Category 0 messages.</span></span> <span data-ttu-id="82ef5-123">Comandos específicos para generar estos tipos de formularios se proporcionan en el siguiente secciones.</span><span class="sxs-lookup"><span data-stu-id="82ef5-123">Specific commands to generate these types of forms are given in the below sections.</span></span>