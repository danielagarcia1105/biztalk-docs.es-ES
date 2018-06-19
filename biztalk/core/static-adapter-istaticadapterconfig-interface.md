---
title: Interfaz IStaticAdapterConfig de adaptador estático | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52f5de01-0cfc-456a-a52b-28f8f076bdfc
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2de8d95ba4a5945cb43e3681055750cdad628759
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277388"
---
# <a name="static-adapter-istaticadapterconfig-interface"></a><span data-ttu-id="29a0a-102">IStaticAdapterConfig de adaptador estático (interfaz)</span><span class="sxs-lookup"><span data-stu-id="29a0a-102">Static Adapter IStaticAdapterConfig Interface</span></span>
<span data-ttu-id="29a0a-103">Un adaptador estático de tiempo de diseño debe implementar la **IStaticAdapterConfig** interfaz.</span><span class="sxs-lookup"><span data-stu-id="29a0a-103">A static design-time adapter must implement the **IStaticAdapterConfig** interface.</span></span> <span data-ttu-id="29a0a-104">Esto le permite interactuar con el Asistente para agregar metadatos de adaptador y obtener del adaptador organizaciones de servicios y descripciones de servicio individual.</span><span class="sxs-lookup"><span data-stu-id="29a0a-104">This allows it to interact with the Add Adapter Metadata Wizard and obtain service organizations and individual service descriptions from the adapter.</span></span> <span data-ttu-id="29a0a-105">Las llamadas del Asistente para la **GetServiceOrganization** y **GetServiceDescription** métodos para extraer información de metadatos con el que el adaptador interactúa y agregarla a un BizTalk project en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29a0a-105">The wizard calls the **GetServiceOrganization** and **GetServiceDescription** methods to pull in metadata information with which the adapter interacts and add it to a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
 <span data-ttu-id="29a0a-106">El **GetServiceOrganization** método obtiene un documento de instancia XML que representa la organización jerárquica de servicios expuestos del adaptador.</span><span class="sxs-lookup"><span data-stu-id="29a0a-106">The **GetServiceOrganization** method obtains an XML instance document that represents the hierarchical organization of the adapter's exposed services.</span></span> <span data-ttu-id="29a0a-107">Esta estructura genera el árbol de organización de servicio que se ve en el **seleccionar servicios para importar** página del Asistente para agregar metadatos de adaptador.</span><span class="sxs-lookup"><span data-stu-id="29a0a-107">This structure generates the service organization tree that you see on the **Select Services to Import** page in the Add Adapter Metadata Wizard.</span></span>  
  
 <span data-ttu-id="29a0a-108">Después de seleccionar los servicios que se va a importar, el asistente llama a la **GetServiceDescription** método para obtener una matriz de archivos de lenguaje de descripción de servicios Web (WSDL) correspondientes a las categorías de servicio que se seleccionaron en el complemento Árbol de Asistente de metadatos de adaptador.</span><span class="sxs-lookup"><span data-stu-id="29a0a-108">After you select the services to import, the wizard calls the **GetServiceDescription** method to obtain an array of Web Services Description Language (WSDL) files corresponding to the service categories that were selected in the Add Adapter Metadata Wizard tree.</span></span> <span data-ttu-id="29a0a-109">Los esquemas que representan los servicios se generan como archivos XSD y se agregan a su proyecto de BizTalk después de completar el Asistente para agregar metadatos de adaptador.</span><span class="sxs-lookup"><span data-stu-id="29a0a-109">Schemas representing the services are generated as XSD files and added to your BizTalk project after you complete the Add Adapter Metadata Wizard.</span></span>  
  
 <span data-ttu-id="29a0a-110">En el ejemplo de adaptador de archivo, el **GetServiceOrganization** y **GetServiceDescription** métodos residen en el **StaticAdapterManagement** clase en el Del archivo de clase.</span><span class="sxs-lookup"><span data-stu-id="29a0a-110">In the file adapter sample, the **GetServiceOrganization** and **GetServiceDescription** methods reside in the **StaticAdapterManagement** class in the AdapterManagement.cs class file.</span></span> <span data-ttu-id="29a0a-111">Las llamadas del Asistente para la **GetServiceOrganization** método para obtener la estructura de árbol para mostrar en el **seleccionar servicios para importar** página.</span><span class="sxs-lookup"><span data-stu-id="29a0a-111">The wizard calls the **GetServiceOrganization** method to obtain the tree structure to display on the **Select Services to Import** page.</span></span> <span data-ttu-id="29a0a-112">En **GetServicesOrganization** el codificado de forma rígida obtener valor del archivo AdapterManagement.CategorySchema.xml se usa tal como se muestra en el siguiente fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="29a0a-112">In **GetServicesOrganization** the hard-coded return value of AdapterManagement.CategorySchema.xml file is used as shown in the following code fragment.</span></span> <span data-ttu-id="29a0a-113">Como programador de adaptadores, necesitará agregar la lógica para devolver el archivo XML adecuado.</span><span class="sxs-lookup"><span data-stu-id="29a0a-113">As an adapter developer you will need to add the logic to return the appropriate XML file.</span></span>  
  
```  
public string GetServiceOrganization(IPropertyBag endPointConfiguration, string NodeIdentifier)   
{  
   string result = GetResource("AdapterManagement.CategorySchema.xml");  
   return result;  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="29a0a-114">No olvide modificar el **GetServiceDescription** método de la **StaticAdapterManagement** (clase) y no de la **DynamicAdapterManagement** (clase), que aparece en primer lugar en el archivo.</span><span class="sxs-lookup"><span data-stu-id="29a0a-114">Be sure to modify the **GetServiceDescription** method of the **StaticAdapterManagement** class, and not of the **DynamicAdapterManagement** class, which appears first in the file.</span></span>  
  
 <span data-ttu-id="29a0a-115">El código siguiente procede del **GetServiceDescription** método del archivo AdapterManagement.cs.</span><span class="sxs-lookup"><span data-stu-id="29a0a-115">The following code is from the **GetServiceDescription** method of the AdapterManagement.cs file.</span></span> <span data-ttu-id="29a0a-116">El archivo service1.wsdl está codificado de forma rígida como el archivo devuelto WSDL.</span><span class="sxs-lookup"><span data-stu-id="29a0a-116">The file service1.wsdl is hard-coded as the WSDL file returned.</span></span> <span data-ttu-id="29a0a-117">Devuelve esquemas representados como archivos WSDL.</span><span class="sxs-lookup"><span data-stu-id="29a0a-117">It returns schemas represented as WSDL files.</span></span> <span data-ttu-id="29a0a-118">El `wsdls` parámetro es una matriz de referencias únicas WSDL correspondientes a las referencias WSDL en el código fuente XML cargado por **GetServicesOrganization**.</span><span class="sxs-lookup"><span data-stu-id="29a0a-118">The `wsdls` parameter is an array of unique WSDL references that correspond to the WSDL references in the source XML loaded by **GetServicesOrganization**.</span></span> <span data-ttu-id="29a0a-119">El conjunto devuelto de descripciones WSDL se utiliza para generar los tipos de puerto y los tipos de mensaje para el proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="29a0a-119">The returned set of WSDL descriptions are used to generate the port types and message types for the BizTalk project.</span></span> <span data-ttu-id="29a0a-120">Si tiene más de un tipo de esquema disponible para la selección en el árbol, necesitará más de un archivo WSDL.</span><span class="sxs-lookup"><span data-stu-id="29a0a-120">If you have more than one schema type available for selection in the tree, you will need more than one WSDL file.</span></span> <span data-ttu-id="29a0a-121">Si tiene varias opciones WSDL y esquemas posibles, quizás desee agregar una búsqueda en base de datos para devolver el archivo correcto WSDL.</span><span class="sxs-lookup"><span data-stu-id="29a0a-121">If you have many possible schema and WSDL choices, you may want to add a database lookup to return the correct WSDL file.</span></span>  
  
```  
/// <summary>     
        /// Get the WSDL file name for the selected WSDL  
        /// </summary>  
        /// <param name="wsdls">place holder</param>  
        /// <returns>An empty string[]</returns>  
        public string[] GetServiceDescription(string[] wsdls)   
      {  
            string[] result = new string[1];  
            result[0] = GetResource("AdapterManagement.service1.wsdl");  
            return result;  
        }  
```  
  
## <a name="see-also"></a><span data-ttu-id="29a0a-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="29a0a-122">See Also</span></span>  
 [<span data-ttu-id="29a0a-123">Configuración estática de adaptador en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="29a0a-123">Static Design-Time Adapter Configuration</span></span>](../core/static-design-time-adapter-configuration.md)