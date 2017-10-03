---
title: "Cómo crear una nueva instancia de un registro existente, el elemento de campo o el nodo de atributo de campo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 02380f68-056c-47c4-a0d6-61d599a4685d
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64f8974de22b7ee99a02d551553cb5e36f31a0d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-new-occurrence-of-an-existing-record-field-element-or-field-attribute-node"></a><span data-ttu-id="b5dfc-102">Cómo crear una nueva instancia de un registro existente, el elemento de campo o el nodo de atributo de campo</span><span class="sxs-lookup"><span data-stu-id="b5dfc-102">How to Create a New Occurrence of an Existing Record, Field Element, or Field Attribute Node</span></span>
<span data-ttu-id="b5dfc-103">Puede crear nuevas instancias de un miembro de **registro**, **elemento de campo**, o **atributo de campo** nodo tal que las modificaciones siguientes en cualquier instancia se reflejan en todos los instancias.</span><span class="sxs-lookup"><span data-stu-id="b5dfc-103">You can create new instances of an existing **Record**, **Field Element**, or **Field Attribute** node such that subsequent modifications to any instance are reflected in all instances.</span></span>  
  
### <a name="to-create-a-new-instance-of-an-existing-record-field-element-or-field-attribute-node"></a><span data-ttu-id="b5dfc-104">Para crear una nueva instancia de un nodo Registro, Elemento de Campo o Atributo de Campo existente</span><span class="sxs-lookup"><span data-stu-id="b5dfc-104">To create a new instance of an existing Record, Field Element, or Field Attribute node</span></span>  
  
1.  <span data-ttu-id="b5dfc-105">Seleccione la versión original **registro**, **elemento de campo**, o **atributo de campo** nodo, asegúrese de que su **Base Data Type** propiedad está establecida correctamente, y, a continuación, en su **Data Structure Type** (**registro** nodos) o su **tipo de datos** (**elemento de campo** y  **Atributo de campo** nodos) propiedad, escriba un nombre de tipo de datos personalizado.</span><span class="sxs-lookup"><span data-stu-id="b5dfc-105">Select the original **Record**, **Field Element**, or **Field Attribute** node, make sure its **Base Data Type** property is set correctly, and then in its **Data Structure Type** (**Record** nodes) or its **Data Type** (**Field Element** and **Field Attribute** nodes) property, type a custom data type name.</span></span>  
  
2.  <span data-ttu-id="b5dfc-106">Insertar el nuevo **registro**, **elemento de campo**, o **atributo de campo** nombre que escribió en el paso 1 de tipo de nodo y establezca una de las siguientes propiedades para los datos personalizados.</span><span class="sxs-lookup"><span data-stu-id="b5dfc-106">Insert the new **Record**, **Field Element**, or **Field Attribute** node and set one of the following properties to the custom data type name you typed in step 1.</span></span>  
  
    -   <span data-ttu-id="b5dfc-107">Tipo de estructura de datos (**registro** nodos)</span><span class="sxs-lookup"><span data-stu-id="b5dfc-107">Data Structure Type (**Record** nodes)</span></span>  
  
    -   <span data-ttu-id="b5dfc-108">Tipo de datos (**elemento de campo** y **atributo de campo** nodos)</span><span class="sxs-lookup"><span data-stu-id="b5dfc-108">Data Type (**Field Element** and **Field Attribute** nodes)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b5dfc-109">Si un nuevo **registro** o **elemento de campo** nodo es un elemento relacionado del nodo original y se asigna al nuevo nodo el mismo nombre que el nodo original, verá un cuadro de mensaje que pregunta sobre nodos duplicados en el mismo ámbito con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="b5dfc-109">If a new **Record** or **Field Element** node is a sibling of the original node, and you give the new node the same name as the original node, you will see a message box asking about duplicate nodes in the same scope with the same name.</span></span> <span data-ttu-id="b5dfc-110">Haga clic en **Sí** realiza la misma acción que elegir el nombre de tipo de datos personalizado en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="b5dfc-110">Clicking **Yes** performs the same action as choosing the custom data type name in step 2.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b5dfc-111">Ha creado una nueva instancia de la existente **registro**, **elemento de campo**, o **atributo de campo** nodo.</span><span class="sxs-lookup"><span data-stu-id="b5dfc-111">You have created a new instance of the existing **Record**, **Field Element**, or **Field Attribute** node.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b5dfc-112">Algunas propiedades de **registro**, **elemento de campo**, o **atributo de campo** instancias de nodo siguen siendo idénticas (un cambio en una instancia es un cambio a todas las instancias) y otras propiedades se pueden establecer de forma independiente para cada instancia.</span><span class="sxs-lookup"><span data-stu-id="b5dfc-112">Some properties of **Record**, **Field Element**, or **Field Attribute** node instances remain identical (a change to one instance is a change to all instances), and other properties can be set independently for each instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5dfc-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5dfc-113">See Also</span></span>  
 [<span data-ttu-id="b5dfc-114">Insertar nodos en un esquema</span><span class="sxs-lookup"><span data-stu-id="b5dfc-114">Inserting Nodes into a Schema</span></span>](../core/inserting-nodes-into-a-schema.md)