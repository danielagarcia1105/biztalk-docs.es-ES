---
title: Cómo probar directivas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, policies
- Business Rule Composer, testing
- Business Rule Composer, policies
- testing, Business Rule Composer
- policies, testing
ms.assetid: 122dee26-d1f1-49a6-a6d5-a9d3d861a66b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7a0f8c0d63d14d5a529039a6e1c8af5b363cc9c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255812"
---
# <a name="how-to-test-policies"></a><span data-ttu-id="ea00f-102">Cómo probar las directivas</span><span class="sxs-lookup"><span data-stu-id="ea00f-102">How to Test Policies</span></span>
<span data-ttu-id="ea00f-103">Para probar una directiva, necesita hechos en los que se puedan ejecutar las reglas.</span><span class="sxs-lookup"><span data-stu-id="ea00f-103">To test a policy, you need facts on which the rules can be executed.</span></span> <span data-ttu-id="ea00f-104">Puede agregar hechos especificando valores en documentos XML o tablas de bases de datos a las que hará referencia en el comprobador de directivas, o puede utilizar un creador de hechos para suministrar al motor una matriz de objetos .NET como hechos.</span><span class="sxs-lookup"><span data-stu-id="ea00f-104">You can add facts by specifying values in XML documents or database tables that you will point to in the policy tester, or you can use a fact creator to supply to the engine an array of .NET objects as facts.</span></span> <span data-ttu-id="ea00f-105">Para obtener más información, consulte [crear un creador de hechos](../core/how-to-create-a-fact-creator.md).</span><span class="sxs-lookup"><span data-stu-id="ea00f-105">For more information, see [Creating a Fact Creator](../core/how-to-create-a-fact-creator.md).</span></span>  
  
### <a name="to-test-a-policy-in-the-business-rule-composer"></a><span data-ttu-id="ea00f-106">Para probar una directiva en el Compositor de reglas de negocio</span><span class="sxs-lookup"><span data-stu-id="ea00f-106">To test a policy in the Business Rule Composer</span></span>  
  
1.  <span data-ttu-id="ea00f-107">En la ventana Explorador de directivas, haga clic en la versión de directiva que desee probar.</span><span class="sxs-lookup"><span data-stu-id="ea00f-107">In the Policy Explorer window, click the policy version that you want to test.</span></span>  
  
2.  <span data-ttu-id="ea00f-108">Haga clic en el **probar directiva** botón (flecha verde) en la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="ea00f-108">Click the **Test Policy** button (green arrow) on the menu bar.</span></span>  
  
     <span data-ttu-id="ea00f-109">El panel superior muestra los tipos de hechos a los que hacen referencia las reglas de directiva.</span><span class="sxs-lookup"><span data-stu-id="ea00f-109">The top pane displays the fact types that the policy rules reference.</span></span>  
  
3.  <span data-ttu-id="ea00f-110">Para agregar una instancia de hechos, haga clic en un **documento XML** o **tabla de base de datos** tipo de datos y, a continuación, haga clic en **Agregar instancia**.</span><span class="sxs-lookup"><span data-stu-id="ea00f-110">To add a fact instance, click an **XML Document** or **Database Table** fact type, and then click **Add Instance**.</span></span>  
  
4.  <span data-ttu-id="ea00f-111">Si desea quitar una instancia de hechos, haga clic en el tipo de hechos correspondiente y, a continuación, haga clic en **quitar instancia**.</span><span class="sxs-lookup"><span data-stu-id="ea00f-111">If you want to remove a fact instance, click the corresponding fact type, and then click **Remove Instance**.</span></span>  
  
5.  <span data-ttu-id="ea00f-112">Si desea agregar un creador de hechos que haya terminado de escribir, haga clic en **agregar** en el panel del creador de hechos.</span><span class="sxs-lookup"><span data-stu-id="ea00f-112">If you want to add a fact creator that you have written, click **Add** in the fact creator pane.</span></span>  
  
6.  <span data-ttu-id="ea00f-113">Haga clic en **prueba**.</span><span class="sxs-lookup"><span data-stu-id="ea00f-113">Click **Test**.</span></span>  
  
     <span data-ttu-id="ea00f-114">Aparece el resultado del seguimiento de pruebas de directivas en la ventana de resultados de la prueba.</span><span class="sxs-lookup"><span data-stu-id="ea00f-114">The policy test trace output appears in the test output window.</span></span>  
  
7.  <span data-ttu-id="ea00f-115">Haga clic con el botón secundario en la ventana de resultados para guardar, borrar, seleccionar o copiar el texto de salida.</span><span class="sxs-lookup"><span data-stu-id="ea00f-115">Right-click in the output window to save, clear, select, or copy the output text.</span></span>  
  
     ![](../core/media/ebiz-testpolicy.gif "ebiz_testpolicy")  
<span data-ttu-id="ea00f-116">Seleccionar un hecho para probar una directiva</span><span class="sxs-lookup"><span data-stu-id="ea00f-116">Selecting fact to test a policy</span></span>