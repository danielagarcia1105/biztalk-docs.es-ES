---
title: "Cómo crear esquemas de propiedad | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24086dea-62b8-4ef6-8af8-eb4ab7c3c018
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 426e98e491ec71a7e430ff6886f5f9820c4b87fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-property-schemas"></a><span data-ttu-id="0b7c7-102">Cómo crear esquemas de propiedades</span><span class="sxs-lookup"><span data-stu-id="0b7c7-102">How to Create Property Schemas</span></span>
<span data-ttu-id="0b7c7-103">Si elige promocionar los campos como campos de propiedades, primero deberá definir un esquema de propiedades.</span><span class="sxs-lookup"><span data-stu-id="0b7c7-103">If you choose to promote fields as property fields, you will need to define a property schema first.</span></span> <span data-ttu-id="0b7c7-104">Este esquema de propiedades especifica una colección no estructurada de campos en la puede promocionar los campos desde un mensaje de instancia definido por un esquema asociado con el esquema de propiedades.</span><span class="sxs-lookup"><span data-stu-id="0b7c7-104">This property schema specifies an unstructured collection of fields into which you can promote fields from within an instance message defined by a schema associated with your property schema.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0b7c7-105">No copie ni edite un esquema de propiedades existente para crear un nuevo esquema.</span><span class="sxs-lookup"><span data-stu-id="0b7c7-105">Do not copy and edit an existing property schema to create a new schema.</span></span> <span data-ttu-id="0b7c7-106">El esquema de propiedades contiene datos internos específicos del esquema.</span><span class="sxs-lookup"><span data-stu-id="0b7c7-106">The property schema contains schema-specific internal data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b7c7-107">No es necesario que cree un esquema de propiedades para promocionar campos distintivos.</span><span class="sxs-lookup"><span data-stu-id="0b7c7-107">You do not need to create a property schema to promote distinguished fields.</span></span>  
  
### <a name="to-create-a-property-schema"></a><span data-ttu-id="0b7c7-108">Para crear un esquema de propiedades</span><span class="sxs-lookup"><span data-stu-id="0b7c7-108">To create a property schema</span></span>  
  
1.  <span data-ttu-id="0b7c7-109">En **el Explorador de soluciones**, haga clic en un proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="0b7c7-109">In **Solution Explorer**, right-click a BizTalk project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="0b7c7-110">En el **Agregar nuevo elemento** cuadro de diálogo, en la **plantillas** sección, haga clic en **esquema de propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0b7c7-110">In the **Add New Item** dialog box, in the **Templates** section, click **Property Schema**.</span></span>  
  
3.  <span data-ttu-id="0b7c7-111">En el **nombre** , escriba un nombre para el esquema y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="0b7c7-111">In the **Name** box, type a name for the schema, and then click **Add**.</span></span>  
  
     <span data-ttu-id="0b7c7-112">Se abre el nuevo esquema de propiedad, y que ya contenga un **elemento de campo** nodo denominado Property1.</span><span class="sxs-lookup"><span data-stu-id="0b7c7-112">The new property schema opens, and it already contains a **Field Element** node named Property1.</span></span>  
  
4.  <span data-ttu-id="0b7c7-113">En el árbol de esquema, haga clic en que **elemento de campo** nodo, haga clic en **cambiar el nombre de**, escriba un nombre descriptivo para la primera propiedad del esquema y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="0b7c7-113">In the schema tree, right-click that **Field Element** node, click **Rename**, type a descriptive name for the first property in the schema, and then press ENTER.</span></span>  
  
5.  <span data-ttu-id="0b7c7-114">Establecer el **tipo de datos** y otras propiedades relevantes, según corresponda, para el **elemento de campo** nodo en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="0b7c7-114">Set the **Data Type** and other relevant properties, as appropriate, for the **Field Element** node in the Properties window.</span></span>  
  
6.  <span data-ttu-id="0b7c7-115">Si desea insertar **elemento de campo** nodos para las propiedades adicionales, haga clic en el \<esquema > nodo, haga clic en **Insertar nodo de esquema**y, a continuación, haga clic en **elemento de campo secundario** y, a continuación, repita los pasos 4 y 5.</span><span class="sxs-lookup"><span data-stu-id="0b7c7-115">If you want to insert **Field Element** nodes for additional properties, right-click the \<Schema> node, click **Insert Schema Node**, and then click **Child Field Element**, and then repeat steps 4 and 5.</span></span> <span data-ttu-id="0b7c7-116">Repita según sea necesario para crear el conjunto necesario de **elemento de campo** nodos en el que se va a promover los valores de los mensajes de instancia.</span><span class="sxs-lookup"><span data-stu-id="0b7c7-116">Repeat as necessary to create the required set of **Field Element** nodes into which you intend to promote values from instance messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b7c7-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b7c7-117">See Also</span></span>  
 [<span data-ttu-id="0b7c7-118">Administrar esquemas en proyectos</span><span class="sxs-lookup"><span data-stu-id="0b7c7-118">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)