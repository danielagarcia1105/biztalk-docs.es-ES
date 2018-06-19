---
title: Conservar delimitadores en el componente de canalización de ensamblador de archivo sin formato | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: adc27561-9996-49a9-b715-e313b9148506
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9d10879adfbe0ca0c68376faa48d9976fc19599
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268788"
---
# <a name="retaining-delimiters-in-the-flat-file-assembler-pipeline-component"></a><span data-ttu-id="f4ae8-102">Conservar delimitadores en el componente de canalización de ensamblador de archivos sin formato</span><span class="sxs-lookup"><span data-stu-id="f4ae8-102">Retaining Delimiters in the Flat File Assembler Pipeline Component</span></span>
<span data-ttu-id="f4ae8-103">Si faltan registros en el mensaje que va a pasar a través de una canalización personalizada que usa el ensamblador de archivo sin formato, el delimitador para dichos registros puede aparecer o no en la salida de archivo sin formato según la ubicación del archivo de entrada en la que faltan los registros.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-103">If there are missing records in the message going through a custom pipeline that uses the Flat File Assembler, the delimiter for those records may or may not appear in the flat file output depending on where in the input file the records are missing.</span></span>  
  
 <span data-ttu-id="f4ae8-104">Para garantizar que el archivo sin formato conserve determinados delimitadores, puede usar una asignación y una secuencia de comandos personalizada para asegurarse de que se ha creado un registro "vacío" cuando no existe un registro de entrada específico en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-104">To ensure that the flat file retain certain delimiters, you can use a map and a custom script to make sure an "empty" record is created when a specific input record does not exist in the message.</span></span> <span data-ttu-id="f4ae8-105">Para que funcione, debe comprobar que los nodos potencialmente vacíos del esquema de documento del ensamblador de archivo sin formato tengan las propiedades siguientes configuradas como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="f4ae8-105">For this to work, you must make sure that the potentially empty nodes in the document schema for the Flat File Assembler have the following properties set as shown:</span></span>  
  
|<span data-ttu-id="f4ae8-106">Propiedad</span><span class="sxs-lookup"><span data-stu-id="f4ae8-106">Property</span></span>|<span data-ttu-id="f4ae8-107">Configuración</span><span class="sxs-lookup"><span data-stu-id="f4ae8-107">Setting</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="f4ae8-108">Conservar delimitador para datos vacíos</span><span class="sxs-lookup"><span data-stu-id="f4ae8-108">Preserve Delimiter for Empty Data</span></span>|<span data-ttu-id="f4ae8-109">Sí</span><span class="sxs-lookup"><span data-stu-id="f4ae8-109">Yes</span></span>|  
|<span data-ttu-id="f4ae8-110">Suprimir delimitadores finales</span><span class="sxs-lookup"><span data-stu-id="f4ae8-110">Suppress Trailing Delimiters</span></span>|<span data-ttu-id="f4ae8-111">No</span><span class="sxs-lookup"><span data-stu-id="f4ae8-111">No</span></span>|  
|<span data-ttu-id="f4ae8-112">Generar nodos vacíos (configurar en el nodo raíz)</span><span class="sxs-lookup"><span data-stu-id="f4ae8-112">Generate Empty Nodes (set this on the root node)</span></span>|<span data-ttu-id="f4ae8-113">True</span><span class="sxs-lookup"><span data-stu-id="f4ae8-113">True</span></span>|  
  
### <a name="to-create-a-map-that-creates-an-empty-record"></a><span data-ttu-id="f4ae8-114">Para crear una asignación que crea un registro "vacío"</span><span class="sxs-lookup"><span data-stu-id="f4ae8-114">To create a map that creates an "empty" record</span></span>  
  
1.  <span data-ttu-id="f4ae8-115">Agregue una nueva asignación al proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-115">Add a new map to your BizTalk project.</span></span>  
  
2.  <span data-ttu-id="f4ae8-116">Especifique el esquema de documento usado por el ensamblador de archivo sin formato como esquema de origen y de destino de la asignación.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-116">Specify the document schema used by the Flat File Assembler as both the map source and map destination schema.</span></span>  
  
3.  <span data-ttu-id="f4ae8-117">Asigne los campos de origen que no estarán vacíos en los correspondientes campos de destino.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-117">Map the source fields that will not be empty to the corresponding destination fields.</span></span>  
  
4.  <span data-ttu-id="f4ae8-118">Para los archivos que pueden estar vacíos, use una secuencia de comandos personalizada para comprobar si el campo de origen está vacío y devuelve una cadena vacía (en lugar de Nulo).</span><span class="sxs-lookup"><span data-stu-id="f4ae8-118">For those fields that may be empty, use a custom script to check if the source field is empty and return an empty string (instead of Nil).</span></span> <span data-ttu-id="f4ae8-119">Use una secuencia de comandos como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="f4ae8-119">Use a script like the following:</span></span>  
  
    ```  
    public string ValOrEmpty(string val)  
    {  
         return (val.Length > 0) ? val : "";  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="f4ae8-120">Debe crear una secuencia de comandos con un nombre de función único para cada campo potencialmente vacío que asigne.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-120">You must create a script with a unique function name for each potentially empty field you map.</span></span> <span data-ttu-id="f4ae8-121">Por ejemplo, si tiene tres campos que pueden estar vacíos, podría tener funciones denominadas `ValOrEmpty1`, `ValOrEmpty2`, `ValOrEmpty3`.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-121">For example, if you have three fields that may be empty, you might have functions named `ValOrEmpty1`, `ValOrEmpty2`, `ValOrEmpty3`.</span></span>  
  
5.  <span data-ttu-id="f4ae8-122">Con la Consola de administración de BizTalk Server, configure el puerto de envío con la canalización personalizada y el componente de ensamblador de archivo sin formato para usar la asignación como asignación saliente.</span><span class="sxs-lookup"><span data-stu-id="f4ae8-122">Using BizTalk Server Administration console, configure the send port with the custom pipeline and flat file assembler component to use the map as an outbound map.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4ae8-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4ae8-123">See Also</span></span>  
 <span data-ttu-id="f4ae8-124">[Cómo configurar asignaciones de salida para un puerto de envío](../core/how-to-configure-outbound-maps-for-a-send-port.md) </span><span class="sxs-lookup"><span data-stu-id="f4ae8-124">[How to Configure Outbound Maps for a Send Port](../core/how-to-configure-outbound-maps-for-a-send-port.md) </span></span>  
 [<span data-ttu-id="f4ae8-125">Componente de canalización de ensamblador de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="f4ae8-125">Flat File Assembler Pipeline Component</span></span>](../core/flat-file-assembler-pipeline-component.md)