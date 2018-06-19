---
title: 'Paso 6: Realizar pruebas de modelo de carga constante para comprobar el rendimiento máximo sostenible | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dd790354-be9f-4278-bd15-493eac8970c9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6bfc0b9670366ab2f38046fcdc5497234b51ba5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302100"
---
# <a name="step-6-perform-constant-load-pattern-tests-to-verify-maximum-sustainable-throughput"></a><span data-ttu-id="c3424-102">Paso 6: Realizar pruebas de modelo de carga constante para comprobar el rendimiento máximo sostenible</span><span class="sxs-lookup"><span data-stu-id="c3424-102">Step 6: Perform Constant Load Pattern Tests to Verify Maximum Sustainable Throughput</span></span>
<span data-ttu-id="c3424-103">Cuando carga probando una solución de BizTalk Server mediante Visual Studio 2010, una prueba del modelo de carga constante debe realizarse una vez que el aproximado máxima sostenible rendimiento (MST) de la solución se determina como se describe en [paso 5: realizar la carga por pasos Pruebas para determinar el rendimiento máximo sostenible de patrón](../technical-guides/step-5-complete-step-load-tests-to-determine-maximum-sustainable-throughput.md).</span><span class="sxs-lookup"><span data-stu-id="c3424-103">When load testing a BizTalk Server solution using Visual Studio 2010, a constant load pattern test should be performed once the approximate Maximum Sustainable Throughput (MST) of the solution is determined as described in [Step 5: Perform Step Load Pattern Tests to Determine Maximum Sustainable Throughput](../technical-guides/step-5-complete-step-load-tests-to-determine-maximum-sustainable-throughput.md).</span></span> <span data-ttu-id="c3424-104">Esto debe hacerse para confirmar que el MST de hecho es sostenible con el tiempo y también con el fin de crear una prueba de carga de la línea de base avanzando evaluar los efectos de los ajustes de rendimiento aplicado a la aplicación de BizTalk Server o el entorno.</span><span class="sxs-lookup"><span data-stu-id="c3424-104">This should be done to confirm that the MST is in fact sustainable over time and also so as to create a baseline load test moving forward to evaluate the effects of any performance tuning applied to the BizTalk Server application or environment.</span></span>  
  
## <a name="create-and-run-a-constant-load-pattern-test"></a><span data-ttu-id="c3424-105">Crear y ejecutar una prueba del modelo de carga constante</span><span class="sxs-lookup"><span data-stu-id="c3424-105">Create and run a Constant Load Pattern Test</span></span>  
 <span data-ttu-id="c3424-106">La manera más fácil de crear una prueba de modelo de carga constante que use la misma combinación de pruebas, conjuntos de contadores y asignaciones de conjuntos de contador utilizado por la prueba de modelo de carga por pasos es simplemente guarde la prueba de modelo de carga por pasos "BTS_Messaging_Step.loadtest" como "BTS_Messaging_ Constant.LoadTest"y, a continuación, realice algunos cambios en"BTS_Messaging_Constant.loadtest".</span><span class="sxs-lookup"><span data-stu-id="c3424-106">The easiest way to create a Constant Load Pattern test that uses the same Test Mix, Counter Sets, and Counter Set Mappings used by the Step Load Pattern test is to simply save the Step Load Pattern test “BTS_Messaging_Step.loadtest” as “BTS_Messaging_Constant.loadtest” and then make some changes to “BTS_Messaging_Constant.loadtest”.</span></span> <span data-ttu-id="c3424-107">Siga estos pasos para crear un modelo de carga constante de prueba que es basado en la prueba de modelo de carga por pasos existente:</span><span class="sxs-lookup"><span data-stu-id="c3424-107">Follow these steps to create a Constant Load Pattern test that is based upon the existing Step Load Pattern test:</span></span>  
  
1.  <span data-ttu-id="c3424-108">Abra BTS_Messaging_Step.loadtest si no está ya abierto.</span><span class="sxs-lookup"><span data-stu-id="c3424-108">Open BTS_Messaging_Step.loadtest if it is not already open.</span></span>  
  
2.  <span data-ttu-id="c3424-109">Haga clic en **archivo** y seleccione **guardar LoadTests\BTS_Messaging_Step.loadtest como**.</span><span class="sxs-lookup"><span data-stu-id="c3424-109">Click **File** and select **Save LoadTests\BTS_Messaging_Step.loadtest As**.</span></span>  
  
3.  <span data-ttu-id="c3424-110">En el **Guardar archivo como** cuadro de diálogo, junto a **nombre de archivo**, escriba C:\Projects\LoadTest\BTSLoad\LoadTests\BTS_Messaging_Constant.loadtest y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="c3424-110">In the **Save File As** dialog box, next to **File name**, enter C:\Projects\LoadTest\BTSLoad\LoadTests\BTS_Messaging_Constant.loadtest and then click **Save**.</span></span>  
  
4.  <span data-ttu-id="c3424-111">En el Editor de prueba de carga, cambiar el nombre del escenario **BTS_Messaging_Step** a **BTS_Messaging_Constant**.</span><span class="sxs-lookup"><span data-stu-id="c3424-111">In the Load Test Editor, rename the scenario **BTS_Messaging_Step** to **BTS_Messaging_Constant**.</span></span> <span data-ttu-id="c3424-112">El nombre del escenario se muestra directamente bajo la **escenarios** carpeta.</span><span class="sxs-lookup"><span data-stu-id="c3424-112">The scenario name is displayed directly under the **Scenarios** folder.</span></span>  
  
5.  <span data-ttu-id="c3424-113">Deje los valores para **combinación de pruebas** y **combinación de redes** sin cambios pero haga clic para seleccionar **modelo de carga por pasos**.</span><span class="sxs-lookup"><span data-stu-id="c3424-113">Leave the values for **Test Mix** and **Network Mix** unchanged but click to select **Step Load Pattern**.</span></span>  
  
6.  <span data-ttu-id="c3424-114">Haga clic en **modelo de carga por pasos** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c3424-114">Right-click **Step Load Pattern** and select **Properties**.</span></span>  
  
7.  <span data-ttu-id="c3424-115">En el **propiedades** sección, en **modelo de carga** haga clic en la lista desplegable junto a **patrón** y cambie el patrón de **paso** a **Constante**.</span><span class="sxs-lookup"><span data-stu-id="c3424-115">In the **Properties** section, under **Load Pattern** click the dropdown list next to **Pattern** and change the Pattern from **Step** to **Constant**.</span></span>  
  
8.  <span data-ttu-id="c3424-116">En el **propiedades** sección, en **parámetros**, cambie el valor de **recuento de usuarios constante** a un valor ligeramente menor que el número de usuarios en el que el patrón de carga de pasos prueba llegaba a ser no sostenible (es decir, el valor de la **BizTalk:Messaging\Documents recibido por / seg** empezó a superar constantemente el valor de **BizTalk:Messaging\Documents procesadas por segundo** y el valor de la **BizTalk cuadro: General Counters\Spool tamaño** comenzó a aumentar sin enlazar).</span><span class="sxs-lookup"><span data-stu-id="c3424-116">In the **Properties** section, under **Parameters**, change the value for **Constant User Count** to a value slightly less than the number of users at which the Step Load Pattern test was becoming unsustainable (i.e. the value for the **BizTalk:Messaging\Documents received per/Sec** began to consistently exceed the value for **BizTalk:Messaging\Documents processed/Sec** and the value of the **BizTalk:Message Box:General Counters\Spool Size** began to increase unbounded).</span></span>  
  
9. <span data-ttu-id="c3424-117">En el **parámetros de ejecución** carpeta, haga clic en **Setting1 ejecutar [Active]** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c3424-117">Under the **Run Settings** folder, right-click **Run Setting1 [Active]** and select **Properties**.</span></span>  
  
10. <span data-ttu-id="c3424-118">Desplácese hacia abajo en la lista de propiedades para el **tiempo** sección y escriba un valor para **duración de la ejecución** de al menos 10 minutos (00:10:00) y compruebe que el valor de **velocidad de muestra** todavía se establece en 5 segundos (00: 00:05).</span><span class="sxs-lookup"><span data-stu-id="c3424-118">Scroll down the list of properties to the **Timing** section and enter a value for **Run Duration** of at least 10 minutes (00:10:00) and verify that the value for **Sample Rate** is still set to 5 seconds (00:00:05).</span></span>  
  
11. <span data-ttu-id="c3424-119">Inicie la prueba de carga haciendo clic en el nombre de la prueba (por ejemplo, BTS_Messaging_Constant) y, a continuación, haga clic en el **Ejecutar prueba** opción de menú.</span><span class="sxs-lookup"><span data-stu-id="c3424-119">Start the load test by right-clicking the test name (e.g. BTS_Messaging_Constant) and then click the **Run Test** menu option.</span></span>