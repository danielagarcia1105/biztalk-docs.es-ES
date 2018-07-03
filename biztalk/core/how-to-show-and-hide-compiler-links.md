---
title: Cómo mostrar y ocultar vínculos de compilador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66bfd9de-c4d2-46ee-854f-cf7c7cd07368
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3c006f5de761837ec1ed0d6f983d380a76a50a5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010053"
---
# <a name="how-to-show-and-hide-compiler-links"></a><span data-ttu-id="4566c-102">Cómo mostrar y ocultar vínculos de compilador</span><span class="sxs-lookup"><span data-stu-id="4566c-102">How to Show and Hide Compiler Links</span></span>
<span data-ttu-id="4566c-103">Al compilar una asignación, el Asignador de BizTalk crea vínculos adicionales, conocidos como vínculos de compilador para contar con todos los vínculos que se necesitan en la asignación.</span><span class="sxs-lookup"><span data-stu-id="4566c-103">When you compile a map, BizTalk Mapper creates additional links, known as compiler links to account for all linking needed in the map.</span></span> <span data-ttu-id="4566c-104">Algunos de estos vínculos no tienen que ver con los vínculos que usted ha creado.</span><span class="sxs-lookup"><span data-stu-id="4566c-104">Some of these links are only implied by the links you created.</span></span> <span data-ttu-id="4566c-105">Cuando compila, o comprueba, una asignación, la línea final de la ventana Resultados de Visual Studio le permite mostrar u ocultar estos vínculos de compilador adicionales en la ventana principal.</span><span class="sxs-lookup"><span data-stu-id="4566c-105">When you compile, or test, a map, the final line in the Visual Studio Output window allows you to show or hide these additional compiler links in the main window.</span></span> <span data-ttu-id="4566c-106">De forma predeterminada, los vínculos de compilador aparecen como líneas discontinuas rojas.</span><span class="sxs-lookup"><span data-stu-id="4566c-106">By default, the compiler links appear as red dashed lines.</span></span>  
  
### <a name="to-show-or-hide-compiler-links"></a><span data-ttu-id="4566c-107">Para mostrar u ocultar los vínculos de compilador</span><span class="sxs-lookup"><span data-stu-id="4566c-107">To show or hide compiler links</span></span>  
  
1. <span data-ttu-id="4566c-108">En el Explorador de soluciones, haga clic en la asignación cuyos vínculos de compilador desea ver y, a continuación, haga clic en **comprobar asignación**.</span><span class="sxs-lookup"><span data-stu-id="4566c-108">In Solution Explorer, right-click the map whose complier links you want to view, and then click **Test Map**.</span></span>  
  
2. <span data-ttu-id="4566c-109">En la ventana Lista de errores de Visual Studio, desplácese hasta el final y haga doble clic en la línea que dice **hacer doble clic aquí para mostrar u ocultar vínculos de compilador**.</span><span class="sxs-lookup"><span data-stu-id="4566c-109">In the Visual Studio Error List window, scroll to the end and double-click the line that says **Double-click here to show/Hide compiler links**.</span></span>  
  
    <span data-ttu-id="4566c-110">Para cambiar el estado de vista de los vínculos de compilador de mostrar a ocultar o de ocultar a mostrar, simplemente haga doble clic en la línea nuevamente.</span><span class="sxs-lookup"><span data-stu-id="4566c-110">To change the display state of compiler links from shown to hidden, or from hidden to shown, just double-click that line again.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4566c-111">Cuando se compilación o vuelve a generar un proyecto de BizTalk o una solución que contiene una o varias asignaciones, el mensaje **hacer doble clic aquí para mostrar u ocultar vínculos de compilador** se muestra en el **lista de errores** ventana de Visual Studio para todas las asignaciones en el proyecto o solución.</span><span class="sxs-lookup"><span data-stu-id="4566c-111">When you build/rebuild a BizTalk project or solution containing one or more maps, the message **Double-click here to show/Hide compiler links** is displayed in the **Error List** window of Visual Studio for all the maps in the project or solution.</span></span>  
  
   <span data-ttu-id="4566c-112">Para comprobar una asignación, debe configurar las propiedades de las instancias de entrada y de salida.</span><span class="sxs-lookup"><span data-stu-id="4566c-112">To test a map, you must configure the properties for the input and output instances.</span></span> <span data-ttu-id="4566c-113">Para obtener más información sobre cómo configurar estas propiedades, vea [cómo configurar la validación del mapa y los parámetros de prueba](../core/how-to-configure-map-validation-and-test-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="4566c-113">For more information about how to configure these properties, see [How to Configure Map Validation and Test Parameters](../core/how-to-configure-map-validation-and-test-parameters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4566c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="4566c-114">See Also</span></span>  
 [<span data-ttu-id="4566c-115">Uso de vínculos para especificar asignaciones de registros y campos</span><span class="sxs-lookup"><span data-stu-id="4566c-115">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)