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
# <a name="schema-categories-in-the-add-adapter-metadata-wizard"></a>Categorías de esquema en el Asistente para agregar metadatos de adaptador

## <a name="overview"></a>Información general
> [!NOTE]
>  Este tema es solo para los adaptadores estáticos que implementan la **IStaticAdapterConfig** interfaz.  
  
 Un adaptador puede usar cualquiera de los miles de esquemas para transformar los datos antes de pasarlo a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Cuando vaya a agregar metadatos a un proyecto de BizTalk, use el Asistente para agregar metadatos de adaptador para seleccionar un esquema en la lista de todos los esquemas con los que el adaptador interactúa.  
  
 En el adaptador de archivo de ejemplo, el archivo CategorySchema.xml es una instancia de esquema que se usa junto al archivo BiztalkAdapterFramework.xsd del marco de trabajo de adaptadores para rellenar una organización de vista en árbol de los esquemas de servicio.  El archivo BizTalkAdapterFramework.xsd se encuentra en la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Developer Tools.  
  
 Debe crear este archivo para que organice los esquemas de manera intuitiva en la solución. Las categorías que ya existen en CategorySchema.xml son simplemente un ejemplo de lo que puede hacer en su propio árbol. No tienen ninguna relevancia concreta para los datos que el adaptador de ejemplo transfiere. La organización de los esquemas resulta bastante importante con los adaptadores específicos de una aplicación, ya que pueden haber miles de esquemas diferentes. En cambio, para los adaptadores específicos de transporte, esta organización de vista en árbol no es necesaria.  
  
 La siguiente ilustración muestra la **seleccionar servicios para importar** página del Asistente para agregar metadatos de adaptador.  
  
 ![](../core/media/ebiz-prog-custad-tree.gif "ebiz_prog_custad_tree")  
Vista de árbol de las categorías de esquema en el Asistente para agregar metadatos de adaptador  


## <a name="sample-xml"></a>Ejemplo de XML
  
 El código siguiente muestra el archivo CategorySchema.xml:  
  
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
  
 Los tipos de nodo siguientes aparecen en esta instancia de esquema:  
  
-   **CategoryTree.** Estructura de nivel superior de un modelo de información del sistema. Puede contener o no nodos CategoryTreeNode, ExpandableCategoryTreeNode y ServiceTreeNode.  
  
-   **CategoryTreeNode.** Puede contener o no CategoryTreeNode y ServiceTreeNode. Use el nodo CategoryTreeNode que aparece como carpeta en la interfaz de usuario para agrupar un conjunto de servicios relacionados. Normalmente, contiene un nombre para mostrar y una descripción de los servicios que se van a mostrar. Un adaptador podría usar CategoryTreeNode si hay pocos nodos secundarios.  
  
-   **ExpandableCategoryTreeNode.** Un nodo hoja que se rellena de forma dinámica al expandirse. ExpandableCategoryTreeNode se usa como marcador de posición y aparece como una carpeta en la interfaz de usuario. Se puede usar para aplazar la acción de rellenar un nodo de categoría con subelementos hasta que el usuario haga clic para expandir el nodo. Un adaptador podría usar ExpandableCategoryTreeNode si una categoría contiene un número grande de nodos secundarios.  
  
-   **ServiceTreeNode.** Un ServiceTreeNode aparece como un documento, o un nodo hoja, en la interfaz de usuario y representa un archivo de Lenguaje de descripción de servicios Web (WSDL).  
  
 Cuando un usuario hace clic en la carpeta para expandir un nodo, el marco de trabajo llama a la **IStaticAdapterConfig.GetServiceOrganization** método en el adaptador pasa el nombre del nodo como el valor de la **NodeIdentifier** atributo. El adaptador debería devolver un CategoryTree que contenga los subnodos para agregar debajo de ExpandableCategoryTreeNode. El marco de trabajo de adaptadores reemplaza ExpandableCategoryTreeNode por CategoryTreeNode y le agrega los elementos secundarios del CategoryTree devuelto.  
  
> [!NOTE]
>  En la llamada inicial a **IStaticAdapterConfig.GetServiceOrganization** el marco de trabajo pasa null para el identificador del nodo. Esto indica al adaptador que devuelva el CategoryTree de nivel raíz.  
  
 A continuación, se muestra el esquema de árbol de categorías extraído del archivo BiztalkAdapterFramework.xsd. El Asistente para agregar metadatos de adaptador lo usa como el árbol esquemático con el que rellenar con entidades dependientes de la aplicación específicas desde un archivo XML. En nuestro ejemplo, este archivo es CategorySchema.xml.  
  
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
  
 Después de modificar el archivo CategorySchema.xml, vuelva a crear el proyecto AdapterManagement y, después, ejecute el Asistente para agregar metadatos de adaptador para asegurarse de que el árbol representado en CategorySchema.xml aparece de forma correcta.  
  
 Para obtener información acerca de cómo ejecutar el Asistente para agregar metadatos de adaptador, vea la **cuadro de diálogo del Asistente de agregar adaptador metadatos** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].