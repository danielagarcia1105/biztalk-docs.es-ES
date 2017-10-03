---
title: Administradores de propiedades | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 823352a0-e397-464a-a163-1dbf8feea8d7
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6aff8fc39612ed79e6e9602ed39874d014bb4a11
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="property-managers"></a><span data-ttu-id="e766b-102">Administradores de propiedades</span><span class="sxs-lookup"><span data-stu-id="e766b-102">Property Managers</span></span>
<span data-ttu-id="e766b-103">Los administradores de propiedades permiten a una extensión agregar propiedades personalizadas (normalmente como anotaciones XSD) a los elementos y atributos de la representación XSD del esquema, así como ampliar la funcionalidad de la ventana Propiedades para incluir propiedades personalizadas asociadas con la extensión.</span><span class="sxs-lookup"><span data-stu-id="e766b-103">Property Managers allow an extension to add custom properties (generally as XSD annotations) to elements and attributes in the XSD representation of the schema, as well as extending the Properties window to include the custom properties associated with the extension.</span></span>  
  
 <span data-ttu-id="e766b-104">Un administrador de propiedades es un objeto que implementa el **IPropertyManager** interfaz, una referencia a la que se obtiene mediante una llamada a **IExtension.GetPropertyManager**y pasar un  **ITreeNode** objeto como parámetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="e766b-104">A Property Manager is an object that implements the **IPropertyManager** interface, a reference to which is obtained by calling **IExtension.GetPropertyManager**, and passing an **ITreeNode** object as the input parameter.</span></span> <span data-ttu-id="e766b-105">Normalmente, la extensión proporciona una **IPropertyManager** para cada objeto **ITreeNode** objeto.</span><span class="sxs-lookup"><span data-stu-id="e766b-105">Typically the extension provides one **IPropertyManager** object for each **ITreeNode** object.</span></span> <span data-ttu-id="e766b-106">El Administrador de propiedades es responsable de la colección de propiedades personalizadas para que **ITreeNode** objeto.</span><span class="sxs-lookup"><span data-stu-id="e766b-106">The Property Manager is responsible for the collection of custom properties for that **ITreeNode** object.</span></span>  
  
 <span data-ttu-id="e766b-107">Una propiedad personalizada se representa mediante un **System.ComponentModel.PropertyDescriptor** objeto, que puede obtenerse de la colección devuelta por la **IPropertyManager.GetProperties** método.</span><span class="sxs-lookup"><span data-stu-id="e766b-107">A custom property is represented by a **System.ComponentModel.PropertyDescriptor** object, which can be obtained from the collection returned by the **IPropertyManager.GetProperties** method.</span></span>  
  
 <span data-ttu-id="e766b-108">Usar **PropertyDescriptor** objetos que representan las propiedades personalizadas asociadas con la extensión facilita la integración con Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="e766b-108">Using **PropertyDescriptor** objects to represent the custom properties associated with the extension facilitates integration with the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window.</span></span> <span data-ttu-id="e766b-109">Cuando **PropertyDescriptor** objetos se utilizan, resulta sencillo para el Editor de BizTalk para integrar las propiedades personalizadas de la extensión en el conjunto de propiedades de nodo estándar ya existentes en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="e766b-109">When **PropertyDescriptor** objects are used, it is easy for BizTalk Editor to integrate the custom properties of the extension into the set of standard node properties already being integrated into the Properties window.</span></span> <span data-ttu-id="e766b-110">Información de propiedad personalizada, como el nombre para mostrar, el valor de presentación, el tipo de control de propiedad, la descripción de propiedad y la categoría de propiedad se obtiene de la **PropertyDescriptor** objeto.</span><span class="sxs-lookup"><span data-stu-id="e766b-110">Custom property information such as the display name, the display value, the type of property control, the property description, and the property category is obtained from the **PropertyDescriptor** object.</span></span>  
  
 <span data-ttu-id="e766b-111">Las propiedades personalizadas se almacenan en la representación XSD del esquema como atributos de un elemento dentro del elemento de anotación del elemento correspondiente al nodo relevante del árbol de esquema.</span><span class="sxs-lookup"><span data-stu-id="e766b-111">Custom properties are stored in the XSD representation of the schema as attributes of an element within the annotation element within the element corresponding to the relevant node in the schema tree.</span></span> <span data-ttu-id="e766b-112">Cada propiedad personalizada de un nodo del árbol de esquema puede ser un atributo de un elemento común o, como alternativa, cada una puede tener su propio elemento asociado.</span><span class="sxs-lookup"><span data-stu-id="e766b-112">Each custom property of a schema tree node can be an attribute of a common element, or alternatively, each can have its own associated element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e766b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="e766b-113">See Also</span></span>  
 [<span data-ttu-id="e766b-114">Extender el Editor de BizTalk</span><span class="sxs-lookup"><span data-stu-id="e766b-114">Extending BizTalk Editor</span></span>](../core/extending-biztalk-editor.md)