---
title: Cómo crear Interfaces de componentes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating component interfaces
- component interfaces, creating
ms.assetid: 9def053a-cbf6-4b34-b2e8-b2d03bffc5fe
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86ee68edba66b05d3c2541dd9c41cc074bd790b7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249300"
---
# <a name="how-to-create-component-interfaces"></a><span data-ttu-id="e007b-102">Cómo crear interfaces de componentes</span><span class="sxs-lookup"><span data-stu-id="e007b-102">How to Create Component Interfaces</span></span>
<span data-ttu-id="e007b-103">Cree interfaces de componentes mediante la aplicación Application Designer de PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="e007b-103">You create component interfaces using the PeopleSoft Application Designer.</span></span> <span data-ttu-id="e007b-104">(Para obtener más información sobre Application Designer, vea la documentación de PeopleSoft Enterprise).</span><span class="sxs-lookup"><span data-stu-id="e007b-104">(For more information about Application Designer, see the PeopleSoft Enterprise documentation.)</span></span>  
  
 <span data-ttu-id="e007b-105">Puede agregar propiedades desde los registros de la vista del componente.</span><span class="sxs-lookup"><span data-stu-id="e007b-105">You can add properties from the records in the component view.</span></span> <span data-ttu-id="e007b-106">En la interfaz del componente puede eliminar una propiedad que no desee que se exponga.</span><span class="sxs-lookup"><span data-stu-id="e007b-106">In the component interface, you can delete a property that you do not want to expose.</span></span> <span data-ttu-id="e007b-107">Puede cambiar el nombre a las propiedades haciendo clic en la propiedad en cuestión y, a continuación, haciendo clic de nuevo hasta que pueda escribir un nuevo nombre.</span><span class="sxs-lookup"><span data-stu-id="e007b-107">You can rename properties by clicking the property and then clicking again until you can type a new name.</span></span> <span data-ttu-id="e007b-108">Si cambia el nombre de una propiedad, puede referirse a ella en la interfaz del componente únicamente por el nuevo nombre y no por el nombre del componente subyacente.</span><span class="sxs-lookup"><span data-stu-id="e007b-108">If you rename a property, you can reference it in the component interface only by the new name, not by the underlying component name.</span></span>  
  
 <span data-ttu-id="e007b-109">Las propiedades pueden tener varios iconos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="e007b-109">Properties may have various icons adjacent to them.</span></span> <span data-ttu-id="e007b-110">Por ejemplo, EMPLID tiene un icono que indica que es un campo clave desde el registro subyacente.</span><span class="sxs-lookup"><span data-stu-id="e007b-110">For example, EMPLID has an icon that indicates that it is a key field from the underlying record.</span></span> <span data-ttu-id="e007b-111">NAME tiene un icono que indica que es un campo de clave alternativo desde el registro subyacente.</span><span class="sxs-lookup"><span data-stu-id="e007b-111">NAME has an icon that indicates that it is an alternate key field from the underlying record.</span></span> <span data-ttu-id="e007b-112">(Para obtener una lista completa de los iconos de las propiedades, vea la documentación de PeopleBooks.)</span><span class="sxs-lookup"><span data-stu-id="e007b-112">(For a complete list of property icons, see the PeopleBooks documentation.)</span></span>  
  
### <a name="creating-a-new-component-interface"></a><span data-ttu-id="e007b-113">Crear una nueva interfaz de componente</span><span class="sxs-lookup"><span data-stu-id="e007b-113">Creating a new component interface</span></span>  
  
1.  <span data-ttu-id="e007b-114">Abra Application Designer de PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="e007b-114">Open the PeopleSoft Application Designer.</span></span>  
  
2.  <span data-ttu-id="e007b-115">En el menú **Archivo** , haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="e007b-115">On the **File** menu, click **New**.</span></span>  
  
     ![](../core/media/psadapter-42-ps-new-compinterface.gif "PSAdapter_42_PS_New_CompInterface")  
  
3.  <span data-ttu-id="e007b-116">En el **New** cuadro de diálogo, seleccione **interfaz de componente**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e007b-116">In the **New** dialog box, select **Component Interface**, and then click **OK**.</span></span>  
  
     ![](../core/media/psadapter-43-ps-selectsourcecomp.gif "PSAdapter_43_PS_SelectSourceComp")  
  
4.  <span data-ttu-id="e007b-117">En el **seleccionar el componente de origen para la interfaz de componente** ventana, seleccione el componente que usar como base para la interfaz de componente y, a continuación, haga clic en **seleccione**.</span><span class="sxs-lookup"><span data-stu-id="e007b-117">In the **Select Source Component for Component Interface** window, select the component to use as a basis for the component interface, and then click **Select**.</span></span>  
  
     ![](../core/media/psadapter-44-ps-appdesigner1.gif "PSAdapter_44_PS_AppDesigner1")  
  
    > [!NOTE]
    >  <span data-ttu-id="e007b-118">Si la interfaz del componente es grande, exponga las propiedades del componente de forma manual.</span><span class="sxs-lookup"><span data-stu-id="e007b-118">If the component interface is large, expose the component properties manually.</span></span>  
  
5.  <span data-ttu-id="e007b-119">En el **Application Designer** diálogo cuadro, elija una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="e007b-119">In the **Application Designer** dialog box, choose one of the following options:</span></span>  
  
    -   <span data-ttu-id="e007b-120">Haga clic en **n** para crear la interfaz de componente sin mostrar las propiedades y exponer propiedades de componente manualmente.</span><span class="sxs-lookup"><span data-stu-id="e007b-120">Click **No** to create the component interface without displaying properties and to expose component properties manually.</span></span>  
  
         <span data-ttu-id="e007b-121">a.</span><span class="sxs-lookup"><span data-stu-id="e007b-121">a.</span></span> <span data-ttu-id="e007b-122">En el panel derecho, arrastre los campos correspondientes en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="e007b-122">Drag the relevant fields from the left pane to the right pane.</span></span>  
  
         <span data-ttu-id="e007b-123">b.</span><span class="sxs-lookup"><span data-stu-id="e007b-123">b.</span></span> <span data-ttu-id="e007b-124">Para seleccionar varias funciones, haga clic en el panel derecho o izquierdo, dependiendo de qué panel está activo.</span><span class="sxs-lookup"><span data-stu-id="e007b-124">To select various functions to perform, right-click either the right or left pane, depending on which pane is active.</span></span>  
  
         <span data-ttu-id="e007b-125">Para obtener una lista completa de las funciones, vea la documentación de PeopleBooks.</span><span class="sxs-lookup"><span data-stu-id="e007b-125">For a complete list of functions, see the PeopleBooks documentation.</span></span>  
  
    -   <span data-ttu-id="e007b-126">Haga clic en **Sí** para crear la interfaz de componentes y mostrar las propiedades de la interfaz del componente subyacente.</span><span class="sxs-lookup"><span data-stu-id="e007b-126">Click **Yes** to create the component interface and display the properties of the underlying component interface.</span></span>  
  
         ![](../core/media/psadapter-45-ps-appdesigner2.gif "PSAdapter_45_PS_AppDesigner2")  
  
## <a name="see-also"></a><span data-ttu-id="e007b-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="e007b-127">See Also</span></span>  
 <span data-ttu-id="e007b-128">[Métodos estándar en Interfaces de componentes](../core/standard-methods-in-component-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="e007b-128">[Standard Methods in Component Interfaces](../core/standard-methods-in-component-interfaces.md) </span></span>  
 <span data-ttu-id="e007b-129">[Apéndice C: usar Interfaces de componentes](../core/appendix-c-using-component-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="e007b-129">[Appendix C: Using Component Interfaces](../core/appendix-c-using-component-interfaces.md) </span></span>  
 [<span data-ttu-id="e007b-130">Apéndice A: métodos de interfaz de componente</span><span class="sxs-lookup"><span data-stu-id="e007b-130">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)