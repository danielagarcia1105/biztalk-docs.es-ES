---
title: Cómo probar Interfaces de componentes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing component interfaces
- component interfaces, testing
ms.assetid: d637f76d-170d-4543-a2b2-a4ac4001386b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be50521e5c4421d8ac8902bcf7a414d734c3b9f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256572"
---
# <a name="how-to-test-component-interfaces"></a><span data-ttu-id="04276-102">Cómo comprobar interfaces de componentes</span><span class="sxs-lookup"><span data-stu-id="04276-102">How to Test Component Interfaces</span></span>
<span data-ttu-id="04276-103">El adaptador de Microsoft BizTalk para PeopleSoft Enterprise utiliza interfaces de componentes y metadatos de PeopleSoft, lo que le permite controlar interfaces de componentes nuevas o modificadas.</span><span class="sxs-lookup"><span data-stu-id="04276-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise uses PeopleSoft metadata and component interfaces; therefore, it can handle new or modified component interfaces.</span></span> <span data-ttu-id="04276-104">El adaptador no realiza suposición alguna de las interfaces de componentes; sólo asume que son lógicas y válidas.</span><span class="sxs-lookup"><span data-stu-id="04276-104">The adapter makes no assumptions about component interfaces except that they are logical and valid.</span></span> <span data-ttu-id="04276-105">Por consiguiente, cada interfaz de componente debe comprobarse antes de que se utilice como origen para el adaptador.</span><span class="sxs-lookup"><span data-stu-id="04276-105">Therefore, each component interface must be tested before it is used as a source for the adapter.</span></span>  
  
 <span data-ttu-id="04276-106">Si el usuario efectúa cambios en la aplicación subyacente, o si tiene lugar una actualización de PeopleSoft, y los cambios invalidan una interfaz de componente, es obligación del usuario reparar la interfaz de componente no válida antes de que el adaptador la utilice.</span><span class="sxs-lookup"><span data-stu-id="04276-106">If changes are made to the underlying application by the user or by a PeopleSoft upgrade, and the changes invalidate a component interface, the user must repair the invalid component interface before the adapter uses it.</span></span>  
  
### <a name="to-test-a-component-interface"></a><span data-ttu-id="04276-107">Para comprobar una interfaz de componente</span><span class="sxs-lookup"><span data-stu-id="04276-107">To test a component interface</span></span>  
  
1.  <span data-ttu-id="04276-108">En el Diseñador de aplicaciones, en la **herramientas** menú, haga clic en **interfaz de componentes de prueba**.</span><span class="sxs-lookup"><span data-stu-id="04276-108">In Application Designer, on the **Tools** menu, click **Test Component Interface**.</span></span>  
  
     ![](../core/media/psadapter-54-ps-testcompinterface1.gif "PSAdapter_54_PS_TestCompInterface1")  
  
2.  <span data-ttu-id="04276-109">En el **comprobación de la interfaz de componente** diálogo cuadro, probar la interfaz de componente utilizando uno de los métodos siguientes.</span><span class="sxs-lookup"><span data-stu-id="04276-109">In the **Component Interface Tester** dialog box, test the component interface by using one the following methods.</span></span> <span data-ttu-id="04276-110">Cuando termine de realizar cambios, haga clic con el botón secundario en el elemento superior del panel.</span><span class="sxs-lookup"><span data-stu-id="04276-110">After you finish making changes, right-click the top item in the pane.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="04276-111">Si fuera necesario, haga clic en el cuadro de diálogo para que pase a primer plano.</span><span class="sxs-lookup"><span data-stu-id="04276-111">If required, click the dialog box to bring it to the foreground.</span></span>  
  
    -   <span data-ttu-id="04276-112">Para probar la interfaz de componente con el método de búsqueda, haga clic en **buscar**.</span><span class="sxs-lookup"><span data-stu-id="04276-112">To test the component interface using the Find method, click **Find**.</span></span>  
  
         <span data-ttu-id="04276-113">El **evaluador de interfaz de componente: resultados de la búsqueda** abre el cuadro de diálogo, mostrar todas las entradas posibles del componente subyacente.</span><span class="sxs-lookup"><span data-stu-id="04276-113">The **Component Interface Tester - Find Results** dialog box opens, displaying all the possible entries for the underlying component.</span></span> <span data-ttu-id="04276-114">Si recupera más de 300 entradas, aparece un mensaje.</span><span class="sxs-lookup"><span data-stu-id="04276-114">If there are more than 300 entries, a message appears.</span></span>  
  
         <span data-ttu-id="04276-115">a.</span><span class="sxs-lookup"><span data-stu-id="04276-115">a.</span></span> <span data-ttu-id="04276-116">En el panel izquierdo de la **resultados de la búsqueda** cuadro de diálogo, seleccione un campo.</span><span class="sxs-lookup"><span data-stu-id="04276-116">In the left pane of the **Find Results** dialog box, select a field.</span></span>  
  
         <span data-ttu-id="04276-117">b.</span><span class="sxs-lookup"><span data-stu-id="04276-117">b.</span></span> <span data-ttu-id="04276-118">Para mostrar los datos relevantes para ese campo concreto, haga clic en **obtener seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="04276-118">To display the relevant data for that particular field, click **Get Selected**.</span></span>  
  
         <span data-ttu-id="04276-119">Aparecerá la pantalla siguiente.</span><span class="sxs-lookup"><span data-stu-id="04276-119">The following screen appears.</span></span>  
  
         ![](../core/media/psadapter-55-ps-testcompinterface2.gif "PSAdapter_55_PS_TestCompInterface2")  
  
         <span data-ttu-id="04276-120">Si la configuración de seguridad lo permite, puede cambiar los valores de los campos individuales.</span><span class="sxs-lookup"><span data-stu-id="04276-120">If the security settings allow, you can change the values in the individual fields.</span></span>  
  
         <span data-ttu-id="04276-121">Se abrirá el cuadro de diálogo siguiente:</span><span class="sxs-lookup"><span data-stu-id="04276-121">The following dialog box opens.</span></span>  
  
         ![](../core/media/psadapter-56-ps-testcompinterface3.gif "PSAdapter_56_PS_TestCompInterface3")  
  
    -   <span data-ttu-id="04276-122">Para comprobar la interfaz de componente con el método `Get`:</span><span class="sxs-lookup"><span data-stu-id="04276-122">To test the component interface using the `Get` method:</span></span>  
  
         <span data-ttu-id="04276-123">a.</span><span class="sxs-lookup"><span data-stu-id="04276-123">a.</span></span> <span data-ttu-id="04276-124">Especifique las claves existentes.</span><span class="sxs-lookup"><span data-stu-id="04276-124">Enter the existing key(s).</span></span>  
  
         <span data-ttu-id="04276-125">b.</span><span class="sxs-lookup"><span data-stu-id="04276-125">b.</span></span> <span data-ttu-id="04276-126">Haga clic en **obtener las propiedades existentes**.</span><span class="sxs-lookup"><span data-stu-id="04276-126">Click **Get Existing**.</span></span>  
  
         <span data-ttu-id="04276-127">De esta manera, recibirá las propiedades expuestas de la clave especificada.</span><span class="sxs-lookup"><span data-stu-id="04276-127">This returns the exposed properties for the key that you entered.</span></span>  
  
         <span data-ttu-id="04276-128">Puede cambiar los valores si **actualizar el acceso** se ha especificado.</span><span class="sxs-lookup"><span data-stu-id="04276-128">You can change values if **Update access** was specified.</span></span>  
  
         <span data-ttu-id="04276-129">También puede comprobar la interfaz con el método `Create`.</span><span class="sxs-lookup"><span data-stu-id="04276-129">Alternatively, you can test using the `Create` method.</span></span>  
  
         ![](../core/media/psadapter-57-ps-testcompinterface4.gif "PSAdapter_57_PS_TestCompInterface4")  
  
    -   <span data-ttu-id="04276-130">Para comprobar la interfaz de componente con el método `Create`:</span><span class="sxs-lookup"><span data-stu-id="04276-130">To test the component interface using the `Create` method:</span></span>  
  
         <span data-ttu-id="04276-131">a.</span><span class="sxs-lookup"><span data-stu-id="04276-131">a.</span></span> <span data-ttu-id="04276-132">Escriba todos los valores de las claves.</span><span class="sxs-lookup"><span data-stu-id="04276-132">Enter all required key values.</span></span>  
  
         <span data-ttu-id="04276-133">b.</span><span class="sxs-lookup"><span data-stu-id="04276-133">b.</span></span> <span data-ttu-id="04276-134">Haga clic en **crear nuevos**.</span><span class="sxs-lookup"><span data-stu-id="04276-134">Click **Create New**.</span></span>  
  
         <span data-ttu-id="04276-135">Al escribir valores válidos en **crear claves**, se abre un panel que muestra los datos de JOBCODE después de expandirse el nombre de tabla con datos predeterminados en su lugar.</span><span class="sxs-lookup"><span data-stu-id="04276-135">When you enter valid values in **Create keys**, a pane that displays the JOBCODE data opens after the Table name is expanded with default data in place.</span></span>  
  
         <span data-ttu-id="04276-136">Ya puede cambiar los campos.</span><span class="sxs-lookup"><span data-stu-id="04276-136">You can change fields now.</span></span>  
  
         ![](../core/media/psadapter-58-ps-testcompinterface5.gif "PSAdapter_58_PS_TestCompInterface5")  
  
         <span data-ttu-id="04276-137">Los cambios se validan comparándolos con la lógica empresarial subyacente.</span><span class="sxs-lookup"><span data-stu-id="04276-137">Changes are validated against the component's underlying business logic.</span></span>  
  
3.  <span data-ttu-id="04276-138">Para guardar los cambios, haga clic en el **guardar** icono.</span><span class="sxs-lookup"><span data-stu-id="04276-138">To save your changes, click the **Save** icon.</span></span>  
  
     <span data-ttu-id="04276-139">Las claves que se han utilizado para crear el registro pueden usarse con el método Get para ver los datos.</span><span class="sxs-lookup"><span data-stu-id="04276-139">The keys used to create the record can be used with the Get method for viewing data.</span></span> <span data-ttu-id="04276-140">Los datos agregados pueden verse en el componente de PeopleSoft, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="04276-140">The data that was added can be viewed in the PeopleSoft Component as shown in the following example.</span></span>  
  
     ![](../core/media/psadapter-59-ps-testcompinterface6.gif "PSAdapter_59_PS_TestCompInterface6")  
  
     <span data-ttu-id="04276-141">**Fecha de vigencia** es uno de los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="04276-141">**Effective Date** is one of the default values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04276-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="04276-142">See Also</span></span>  
 <span data-ttu-id="04276-143">[Apéndice A: métodos de interfaz de componente](../core/appendix-a-component-interface-methods.md) </span><span class="sxs-lookup"><span data-stu-id="04276-143">[Appendix A: Component Interface Methods](../core/appendix-a-component-interface-methods.md) </span></span>  
 [<span data-ttu-id="04276-144">Apéndice C: usar Interfaces de componentes</span><span class="sxs-lookup"><span data-stu-id="04276-144">Appendix C: Using Component Interfaces</span></span>](../core/appendix-c-using-component-interfaces.md)