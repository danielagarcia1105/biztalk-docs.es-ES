---
title: Preguntas y respuestas de solución de problemas generales | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2f89d92-0a97-4017-8b8e-6afd8b20eaf4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a47cfd0bc1d2de1ad044712c12b97260981e610
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010653"
---
# <a name="general-troubleshooting-questions-and-answers"></a><span data-ttu-id="86d04-102">Preguntas y respuestas generales de solución de problemas</span><span class="sxs-lookup"><span data-stu-id="86d04-102">General Troubleshooting Questions and Answers</span></span>
<span data-ttu-id="86d04-103">En este tema se incluyen preguntas y respuestas para ayudarle a resolver problemas con el Asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="86d04-103">This topic has questions and answers to help you resolve issues with the BizTalk Mapper.</span></span>  
  
## <a name="how-do-i-specify-xslt-output-settings"></a><span data-ttu-id="86d04-104">¿Cómo especifico la configuración de salida XSLT?</span><span class="sxs-lookup"><span data-stu-id="86d04-104">How do I specify XSLT output settings?</span></span>  
 <span data-ttu-id="86d04-105">Puede usar el Asignador de BizTalk para incluir u omitir declaraciones XML y controlar la codificación usada para los datos de instancia de salida.</span><span class="sxs-lookup"><span data-stu-id="86d04-105">You can use the BizTalk Mapper to include or omit XML declarations, and control the encoding used for output instance data.</span></span>  
  
#### <a name="include-or-exclude-an-xml-declaration"></a><span data-ttu-id="86d04-106">Incluir o excluir una declaración XML</span><span class="sxs-lookup"><span data-stu-id="86d04-106">Include or exclude an XML declaration</span></span>  
  
1.  <span data-ttu-id="86d04-107">En la vista Cuadrícula, haga clic en la cuadrícula del Asignador.</span><span class="sxs-lookup"><span data-stu-id="86d04-107">In the Grid view, click the mapper grid.</span></span> <span data-ttu-id="86d04-108">El **propiedades** ventana muestra las propiedades de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="86d04-108">The **Properties** window displays the grid properties.</span></span>  
  
2.  <span data-ttu-id="86d04-109">En la lista desplegable para la **omitir declaración XML** propiedad, seleccione **Sí** para omitir una declaración XML, o bien seleccione **No** no para omitir una declaración XML.</span><span class="sxs-lookup"><span data-stu-id="86d04-109">In the drop-down list for the **Omit XML Declaration** property, select **Yes** to omit an XML declaration, or select **No** not to omit an XML declaration.</span></span>  
  
#### <a name="set-encoding-for-output-instance-data"></a><span data-ttu-id="86d04-110">Establecer la codificación de datos de instancia de salida</span><span class="sxs-lookup"><span data-stu-id="86d04-110">Set encoding for output instance data</span></span>  
  
1.  <span data-ttu-id="86d04-111">En la vista Cuadrícula, haga clic en la cuadrícula del Asignador.</span><span class="sxs-lookup"><span data-stu-id="86d04-111">In the Grid view, click the mapper grid.</span></span> <span data-ttu-id="86d04-112">El **propiedades** ventana muestra las propiedades de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="86d04-112">The **Properties** window displays the grid properties.</span></span>  
  
2.  <span data-ttu-id="86d04-113">En la lista desplegable para la **codificación XSLT** propiedad, seleccione el juego de caracteres desea usar para los datos de instancia de salida.</span><span class="sxs-lookup"><span data-stu-id="86d04-113">In the drop-down list for the **XSLT Encoding** property, select the character set you want to use for the output instance data.</span></span>  
  
## <a name="how-do-i-create-multipart-mappings"></a><span data-ttu-id="86d04-114">¿Cómo creo asignaciones de varias partes?</span><span class="sxs-lookup"><span data-stu-id="86d04-114">How do I create multipart mappings?</span></span>  
 <span data-ttu-id="86d04-115">Si tiene varias asignaciones que se usan juntas, necesitará combinarlas en una orquestación mediante el **transformar** forma para probarlas conjuntamente.</span><span class="sxs-lookup"><span data-stu-id="86d04-115">If you have multiple maps that are used together, you will need to combine them in an orchestration by using the **Transform** shape to test them together.</span></span> <span data-ttu-id="86d04-116">El Asignador de BizTalk solo puede probar una asignación cada vez.</span><span class="sxs-lookup"><span data-stu-id="86d04-116">The BizTalk Mapper can test only one map at a time.</span></span>  
  
## <a name="why-isnt-my-database-functoid-working"></a><span data-ttu-id="86d04-117">¿Por qué mi functoid de bases de datos no funciona?</span><span class="sxs-lookup"><span data-stu-id="86d04-117">Why isn't my database functoid working?</span></span>  
 <span data-ttu-id="86d04-118">Los functoids de base de datos **búsqueda de la base de datos** y **Extractor de valor** no devuelven directamente información de error; en su lugar, capturan la información y para proporcionar el **dedevolucióndeError** functoid para su uso por la asignación.</span><span class="sxs-lookup"><span data-stu-id="86d04-118">The database functoids **Database Lookup** and **Value Extractor** do not directly return error information; rather, they capture the information and supply it to the **Error Return** functoid for use by your map.</span></span> <span data-ttu-id="86d04-119">Puede usar el **devolución de Error** functoid para la detección de errores en los escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="86d04-119">You can use the **Error Return** functoid for error detection as in the following scenarios:</span></span>  
  
- <span data-ttu-id="86d04-120">Cuando la asignación tiene un **búsqueda de la base de datos** o **Extractor de valor** functoid que no se comporta según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="86d04-120">When your map has a **Database Lookup** or **Value Extractor** functoid that is not behaving as expected.</span></span> <span data-ttu-id="86d04-121">Para ver el mensaje de error, asigne de forma temporal el functoid a un campo en el esquema de salida.</span><span class="sxs-lookup"><span data-stu-id="86d04-121">To see the error message, temporarily map the functoid to a field in the output schema.</span></span>  
  
- <span data-ttu-id="86d04-122">Si su aplicación espera otro contenido de mensaje cuando se producen errores en las operaciones de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="86d04-122">If your application expects different message content when database operations fail.</span></span> <span data-ttu-id="86d04-123">Puede usar el **devolución de Error** functoid para detectar un error y el mensaje de error se asignan a una estructura alternativa para que las aplicaciones de nivel inferiores pueden reaccionar de manera controlada.</span><span class="sxs-lookup"><span data-stu-id="86d04-123">You can use the **Error Return** functoid to detect an error and map the error message to an alternate structure so that downstream applications can react in a controlled manner.</span></span>  
  
  <span data-ttu-id="86d04-124">Para evitar errores que se detectan en tiempo de ejecución, asegúrese de que el primer parámetro para el **devolución de Error** functoid es el resultado de una **búsqueda de la base de datos** functoid y no la salida de otro functoid en la Categoría de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="86d04-124">To avoid errors that are detected only at run time, make sure that the first parameter to the **Error Return** functoid is the output of a **Database Lookup** functoid and not the output of any other functoid in the Database category.</span></span>  
  
  <span data-ttu-id="86d04-125">Para obtener más información sobre el uso de la **devolución de Error** functoid (incluido un ejemplo), consulte el **referencia de Functoid** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="86d04-125">For more information about using the **Error Return** functoid (including a sample), see the **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="why-is-my-map-failing-when-calling-my-custom-functoid"></a><span data-ttu-id="86d04-126">¿Por qué se producen errores en mi asignación cuando llamo a mi functoid personalizado?</span><span class="sxs-lookup"><span data-stu-id="86d04-126">Why is my map failing when calling my custom functoid?</span></span>  
 <span data-ttu-id="86d04-127">Los functoids personalizados debe estar instalados en la caché de ensamblados global (GAC) en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo antes de que se pueden invocar en un mapa.</span><span class="sxs-lookup"><span data-stu-id="86d04-127">Custom functoids must be installed into the global assembly cache (GAC) on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer before they can be invoked by a map.</span></span> <span data-ttu-id="86d04-128">Compruebe que en ensamblado que contiene el functoid personalizado se ha firmado y colocado en la GAC.</span><span class="sxs-lookup"><span data-stu-id="86d04-128">Verify that the assembly containing your custom functoid has been signed and placed into the GAC.</span></span> <span data-ttu-id="86d04-129">Copie también el ensamblado en la carpeta “%BTSINSTALLPATH%\Developer Tools\Mapper Extensions”.</span><span class="sxs-lookup"><span data-stu-id="86d04-129">Also, copy the assembly into the folder “%BTSINSTALLPATH%\Developer Tools\Mapper Extensions”.</span></span>  
  
 <span data-ttu-id="86d04-130">Para obtener más información acerca de cómo instalar ensamblados en la GAC, consulte [instalación del ensamblado en la GAC](../core/assembly-installation-in-the-gac.md).</span><span class="sxs-lookup"><span data-stu-id="86d04-130">For more information about installing assemblies to the GAC, see [Assembly Installation in the GAC](../core/assembly-installation-in-the-gac.md).</span></span> <span data-ttu-id="86d04-131">Para ver los ensamblados instalados en la GAC, desplácese al directorio del ensamblado de su [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] directorio de instalación.</span><span class="sxs-lookup"><span data-stu-id="86d04-131">To view assemblies installed in the GAC, navigate to the Assembly directory of your [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] installation directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86d04-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="86d04-132">See Also</span></span>  
 [<span data-ttu-id="86d04-133">Solución de problemas de mapas</span><span class="sxs-lookup"><span data-stu-id="86d04-133">Troubleshooting Maps</span></span>](../core/troubleshooting-maps.md)