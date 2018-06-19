---
title: Categorías de esquema en los metadatos de Asistente para agregar adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3927c676-f60a-449e-be43-6f75e28aefe1
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fda24ee5ef4993c90eb82e0f406da2e06618776
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271508"
---
# <a name="schema-categories-in-the-add-adapter-metadata-wizard"></a><span data-ttu-id="cf482-102">Categorías de esquema en el Asistente para agregar metadatos de adaptador</span><span class="sxs-lookup"><span data-stu-id="cf482-102">Schema Categories in the Add Adapter Metadata Wizard</span></span>

## <a name="overview"></a><span data-ttu-id="cf482-103">Información general</span><span class="sxs-lookup"><span data-stu-id="cf482-103">Overview</span></span>
> [!NOTE]
>  <span data-ttu-id="cf482-104">Este tema es solo para los adaptadores estáticos que implementan la **IStaticAdapterConfig** interfaz.</span><span class="sxs-lookup"><span data-stu-id="cf482-104">This topic is only for static adapters that implement the **IStaticAdapterConfig** interface.</span></span>  
  
 <span data-ttu-id="cf482-105">Un adaptador puede usar cualquiera de los miles de esquemas para transformar los datos antes de pasarlo a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf482-105">An adapter may use any one of thousands of schemas to transform data before passing it to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="cf482-106">Cuando vaya a agregar metadatos a un proyecto de BizTalk, use el Asistente para agregar metadatos de adaptador para seleccionar un esquema en la lista de todos los esquemas con los que el adaptador interactúa.</span><span class="sxs-lookup"><span data-stu-id="cf482-106">When adding metadata to a BizTalk project, use the Add Adapter Metadata Wizard to select a schema from a list of all the schemas with which the adapter interacts.</span></span>  
  
 <span data-ttu-id="cf482-107">En el adaptador de archivo de ejemplo, el archivo CategorySchema.xml es una instancia de esquema que se usa junto al archivo BiztalkAdapterFramework.xsd del marco de trabajo de adaptadores para rellenar una organización de vista en árbol de los esquemas de servicio.</span><span class="sxs-lookup"><span data-stu-id="cf482-107">In the sample file adapter, the CategorySchema.xml file is a schema instance that is used in conjunction with the Adapter Framework's BiztalkAdapterFramework.xsd file to populate a tree-view organization of service schemas.</span></span>  <span data-ttu-id="cf482-108">El archivo BizTalkAdapterFramework.xsd se encuentra en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Developer Tools.</span><span class="sxs-lookup"><span data-stu-id="cf482-108">The BizTalkAdapterFramework.xsd file is located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Developer Tools folder.</span></span>  
  
 <span data-ttu-id="cf482-109">Debe crear este archivo para que organice los esquemas de manera intuitiva en la solución.</span><span class="sxs-lookup"><span data-stu-id="cf482-109">You should create this file so that it organizes the schemas in a manner that is intuitive to your solution.</span></span> <span data-ttu-id="cf482-110">Las categorías que ya existen en CategorySchema.xml son simplemente un ejemplo de lo que puede hacer en su propio árbol.</span><span class="sxs-lookup"><span data-stu-id="cf482-110">The existing categories in CategorySchema.xml are just an example of what you can do in your own tree.</span></span> <span data-ttu-id="cf482-111">No tienen ninguna relevancia concreta para los datos que el adaptador de ejemplo transfiere.</span><span class="sxs-lookup"><span data-stu-id="cf482-111">The categories do not have any particular relevance to the data that is passed by the sample adapter.</span></span> <span data-ttu-id="cf482-112">La organización de los esquemas resulta bastante importante con los adaptadores específicos de una aplicación, ya que pueden haber miles de esquemas diferentes.</span><span class="sxs-lookup"><span data-stu-id="cf482-112">The organization of the schemas is particularly important with application-specific adapters, where thousands of different schemas may be available.</span></span> <span data-ttu-id="cf482-113">En cambio, para los adaptadores específicos de transporte, esta organización de vista en árbol no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="cf482-113">For transport-specific adapters, this tree-view organization is unnecessary.</span></span>  
  
 <span data-ttu-id="cf482-114">La siguiente ilustración muestra la **seleccionar servicios para importar** página del Asistente para agregar metadatos de adaptador.</span><span class="sxs-lookup"><span data-stu-id="cf482-114">The following figure shows the **Select Services to Import** page in the Add Adapter Metadata Wizard.</span></span>  
  
 ![](../core/media/ebiz-prog-custad-tree.gif "ebiz_prog_custad_tree")  
<span data-ttu-id="cf482-115">Vista de árbol de las categorías de esquema en el Asistente para agregar metadatos de adaptador</span><span class="sxs-lookup"><span data-stu-id="cf482-115">Tree view of the schema categories in the Add Adapter Metadata Wizard</span></span>  


## <a name="sample-xml"></a><span data-ttu-id="cf482-116">Ejemplo de XML</span><span class="sxs-lookup"><span data-stu-id="cf482-116">Sample XML</span></span>
  
 <span data-ttu-id="cf482-117">El código siguiente muestra el archivo CategorySchema.xml:</span><span class="sxs-lookup"><span data-stu-id="cf482-117">The following code shows the CategorySchema.xml file:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<CategoryTree>  
     <DisplayName>Services Organization</DisplayName>  
     <DisplayDescription>An organization of application services</DisplayDescription>  
     <CategoryTreeNode>  
          <DisplayName>Health Care</DisplayName>  
          <Description>Services under Health Care</Description>  
          <CategoryTreeNode>  
               <DisplayName>Administrative</DisplayName>  
               <Description>Administrative Health Care Services</Description>  
               <ServiceTreeNode>  
                    <DisplayName>Eligibility</DisplayName>  
                    <Description>Eligibility Verification Transactions</Description>  
                    <WSDLReference>ANSI X 12 270</WSDLReference>  
               </ServiceTreeNode>  
          </CategoryTreeNode>  
     </CategoryTreeNode>  
     <CategoryTreeNode>  
          <DisplayName>Manufacturing</DisplayName>  
          <Description>Manufacturing Services</Description>  
          <CategoryTreeNode>  
               <DisplayName>Inventory</DisplayName>  
               <Description>Inventory Services</Description>  
               <ServiceTreeNode>  
                    <DisplayName>Requisition</DisplayName>  
                    <Description>Requisition</Description>  
                    <WSDLReference>RequisitionService</WSDLReference>  
               </ServiceTreeNode>  
          </CategoryTreeNode>  
     </CategoryTreeNode>  
</CategoryTree>  
```  
  
 <span data-ttu-id="cf482-118">Los tipos de nodo siguientes aparecen en esta instancia de esquema:</span><span class="sxs-lookup"><span data-stu-id="cf482-118">The following node types appear in this schema instance:</span></span>  
  
-   <span data-ttu-id="cf482-119">**CategoryTree.**</span><span class="sxs-lookup"><span data-stu-id="cf482-119">**CategoryTree.**</span></span> <span data-ttu-id="cf482-120">Estructura de nivel superior de un modelo de información del sistema.</span><span class="sxs-lookup"><span data-stu-id="cf482-120">Top-level structure of a model of system information.</span></span> <span data-ttu-id="cf482-121">Puede contener o no nodos CategoryTreeNode, ExpandableCategoryTreeNode y ServiceTreeNode.</span><span class="sxs-lookup"><span data-stu-id="cf482-121">Contains zero or more of the CategoryTreeNode, ExpandableCategoryTreeNode, and ServiceTreeNode nodes.</span></span>  
  
-   <span data-ttu-id="cf482-122">**CategoryTreeNode.**</span><span class="sxs-lookup"><span data-stu-id="cf482-122">**CategoryTreeNode.**</span></span> <span data-ttu-id="cf482-123">Puede contener o no CategoryTreeNode y ServiceTreeNode.</span><span class="sxs-lookup"><span data-stu-id="cf482-123">Contains zero or more CategoryTreeNode and ServiceTreeNode nodes.</span></span> <span data-ttu-id="cf482-124">Use el nodo CategoryTreeNode que aparece como carpeta en la interfaz de usuario para agrupar un conjunto de servicios relacionados.</span><span class="sxs-lookup"><span data-stu-id="cf482-124">Use the CategoryTreeNode that appears as a folder in the user interface (UI) to group a set of related services.</span></span> <span data-ttu-id="cf482-125">Normalmente, contiene un nombre para mostrar y una descripción de los servicios que se van a mostrar.</span><span class="sxs-lookup"><span data-stu-id="cf482-125">Typically this contains a display name and description of the services to be displayed.</span></span> <span data-ttu-id="cf482-126">Un adaptador podría usar CategoryTreeNode si hay pocos nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="cf482-126">An adapter might use a CategoryTreeNode if the number of child nodes is small.</span></span>  
  
-   <span data-ttu-id="cf482-127">**ExpandableCategoryTreeNode.**</span><span class="sxs-lookup"><span data-stu-id="cf482-127">**ExpandableCategoryTreeNode.**</span></span> <span data-ttu-id="cf482-128">Un nodo hoja que se rellena de forma dinámica al expandirse.</span><span class="sxs-lookup"><span data-stu-id="cf482-128">A leaf node that is dynamically populated when expanded.</span></span> <span data-ttu-id="cf482-129">ExpandableCategoryTreeNode se usa como marcador de posición y aparece como una carpeta en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="cf482-129">The ExpandableCategoryTreeNode is used as a placeholder and appears as a folder in the UI.</span></span> <span data-ttu-id="cf482-130">Se puede usar para aplazar la acción de rellenar un nodo de categoría con subelementos hasta que el usuario haga clic para expandir el nodo.</span><span class="sxs-lookup"><span data-stu-id="cf482-130">This can be used to defer populating a category node with subelements until the user clicks to expand the node.</span></span> <span data-ttu-id="cf482-131">Un adaptador podría usar ExpandableCategoryTreeNode si una categoría contiene un número grande de nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="cf482-131">An adapter might use an ExpandableCategoryTreeNode if a category contains a large number of child nodes.</span></span>  
  
-   <span data-ttu-id="cf482-132">**ServiceTreeNode.**</span><span class="sxs-lookup"><span data-stu-id="cf482-132">**ServiceTreeNode.**</span></span> <span data-ttu-id="cf482-133">Un ServiceTreeNode aparece como un documento, o un nodo hoja, en la interfaz de usuario y representa un archivo de Lenguaje de descripción de servicios Web (WSDL).</span><span class="sxs-lookup"><span data-stu-id="cf482-133">A ServiceTreeNode appears as a document, or leaf node, in the UI and represents a Web Services Description Language (WSDL) file.</span></span>  
  
 <span data-ttu-id="cf482-134">Cuando un usuario hace clic en la carpeta para expandir un nodo, el marco de trabajo llama a la **IStaticAdapterConfig.GetServiceOrganization** método en el adaptador pasa el nombre del nodo como el valor de la **NodeIdentifier** atributo.</span><span class="sxs-lookup"><span data-stu-id="cf482-134">When a user clicks the folder to expand a node, the Adapter Framework calls the **IStaticAdapterConfig.GetServiceOrganization** method on the adapter passing the name of the node as the value of the **NodeIdentifier** attribute.</span></span> <span data-ttu-id="cf482-135">El adaptador debería devolver un CategoryTree que contenga los subnodos para agregar debajo de ExpandableCategoryTreeNode.</span><span class="sxs-lookup"><span data-stu-id="cf482-135">The adapter should return a CategoryTree containing the subnodes to add under the ExpandableCategoryTreeNode.</span></span> <span data-ttu-id="cf482-136">El marco de trabajo de adaptadores reemplaza ExpandableCategoryTreeNode por CategoryTreeNode y le agrega los elementos secundarios del CategoryTree devuelto.</span><span class="sxs-lookup"><span data-stu-id="cf482-136">The Adapter Framework replaces the ExpandableCategoryTreeNode with a CategoryTreeNode and adds to it the children of the returned CategoryTree.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf482-137">En la llamada inicial a **IStaticAdapterConfig.GetServiceOrganization** el marco de trabajo pasa null para el identificador del nodo.</span><span class="sxs-lookup"><span data-stu-id="cf482-137">In the initial call to **IStaticAdapterConfig.GetServiceOrganization** the Adapter Framework passes null for the node identifier.</span></span> <span data-ttu-id="cf482-138">Esto indica al adaptador que devuelva el CategoryTree de nivel raíz.</span><span class="sxs-lookup"><span data-stu-id="cf482-138">This tells the adapter to return the root-level CategoryTree.</span></span>  
  
 <span data-ttu-id="cf482-139">A continuación, se muestra el esquema de árbol de categorías extraído del archivo BiztalkAdapterFramework.xsd.</span><span class="sxs-lookup"><span data-stu-id="cf482-139">Below is the category tree schema extracted from the BiztalkAdapterFramework.xsd file.</span></span> <span data-ttu-id="cf482-140">El Asistente para agregar metadatos de adaptador lo usa como el árbol esquemático con el que rellenar con entidades dependientes de la aplicación específicas desde un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="cf482-140">This is used by the Add Adapter Metadata Wizard as the skeleton tree with which to populate with specific application-dependent entities from an XML file.</span></span> <span data-ttu-id="cf482-141">En nuestro ejemplo, este archivo es CategorySchema.xml.</span><span class="sxs-lookup"><span data-stu-id="cf482-141">In our example that file is the CategorySchema.xml file.</span></span>  
  
```  
<!-- Service Organization Tree schema used by Add Adapter Wizard -->  
    <xs:element name="CategoryTree" type="CategoryTree" />  
    <xs:complexType name="CategoryTree">  
        <xs:sequence>  
            <xs:element name="DisplayName" type="xs:string" />  
            <xs:element name="DisplayDescription" type="xs:string" />  
            <xs:choice minOccurs="0" maxOccurs="unbounded">  
                <xs:element name="ExpandableCategoryTreeNode" type="ExpandableCategoryTreeNode" minOccurs="0" maxOccurs="unbounded" />  
                <xs:element name="CategoryTreeNode" type="CategoryTreeNode" minOccurs="0" maxOccurs="unbounded" />  
                <xs:element name="ServiceTreeNode" type="ServiceTreeNode" minOccurs="0" maxOccurs="unbounded" />  
            </xs:choice>  
        </xs:sequence>  
    </xs:complexType>  
    <xs:complexType name="ExpandableCategoryTreeNode">  
        <xs:sequence>  
            <xs:element name="DisplayName" type="xs:string" />  
            <xs:element name="Description" type="xs:string" />  
        </xs:sequence>  
        <xs:attribute name="NodeIdentifier" type="xs:string" use="required"></xs:attribute>  
    </xs:complexType>  
    <xs:complexType name="CategoryTreeNode">  
        <xs:sequence>  
            <xs:element name="DisplayName" type="xs:string" />  
            <xs:element name="Description" type="xs:string" />  
            <xs:choice minOccurs="0" maxOccurs="unbounded">  
                <xs:element name="ExpandableCategoryTreeNode" type="ExpandableCategoryTreeNode" minOccurs="0" maxOccurs="unbounded" />  
                <xs:element name="CategoryTreeNode" type="CategoryTreeNode" minOccurs="0" maxOccurs="unbounded" />  
                <xs:element name="ServiceTreeNode" type="ServiceTreeNode" minOccurs="0" maxOccurs="unbounded" />  
            </xs:choice>  
        </xs:sequence>  
    </xs:complexType>  
    <xs:complexType name="ServiceTreeNode">  
        <xs:sequence>  
            <xs:element name="DisplayName" type="xs:string" />  
            <xs:element name="Description" type="xs:string" />  
            <xs:element name="WSDLReference" type="xs:string" />  
        </xs:sequence>  
    </xs:complexType>  
</xs:schema>  
```  
  
 <span data-ttu-id="cf482-142">Después de modificar el archivo CategorySchema.xml, vuelva a crear el proyecto AdapterManagement y, después, ejecute el Asistente para agregar metadatos de adaptador para asegurarse de que el árbol representado en CategorySchema.xml aparece de forma correcta.</span><span class="sxs-lookup"><span data-stu-id="cf482-142">After modifying your CategorySchema.xml file, rebuild the AdapterManagement project, and then run the Add Adapter Metadata Wizard to ensure that the tree represented in CategorySchema.xml appears correctly.</span></span>  
  
 <span data-ttu-id="cf482-143">Para obtener información acerca de cómo ejecutar el Asistente para agregar metadatos de adaptador, vea la **cuadro de diálogo del Asistente de agregar adaptador metadatos** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="cf482-143">For information about running the Add Adapter Metadata Wizard, see the **Add Adapter Metadata Wizard Dialog Box** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>