---
title: Invocar miembros estáticos de una clase | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a51171c-8de0-45dd-8659-f674cf27acbe
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2128bf6cb71c773cd31be497765e39b0d7815b4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262276"
---
# <a name="invoking-static-members-of-a-class"></a><span data-ttu-id="fef16-102">Invocar miembros estáticos de una clase</span><span class="sxs-lookup"><span data-stu-id="fef16-102">Invoking Static Members of a Class</span></span>
<span data-ttu-id="fef16-103">De forma predeterminada, el motor de reglas necesita que imponga una instancia de una clase .NET para ejecutar una directiva que invoque un miembro estático de la clase .NET.</span><span class="sxs-lookup"><span data-stu-id="fef16-103">By default, the rule engine requires you to assert an instance of a .NET class to execute a policy that invokes a static member of the .NET class.</span></span> <span data-ttu-id="fef16-104">Puede modificar este comportamiento si cambia el valor de la **StaticSupport** clave del registro bajo **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0** a uno de los valores en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="fef16-104">You can modify this behavior by changing the value of the **StaticSupport** registry key under **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0** to one of the values in the following table.</span></span>  
  
|<span data-ttu-id="fef16-105">Valor del Registro StaticSupport</span><span class="sxs-lookup"><span data-stu-id="fef16-105">StaticSupport registry value</span></span>|<span data-ttu-id="fef16-106">Comportamiento del motor de reglas</span><span class="sxs-lookup"><span data-stu-id="fef16-106">Rule engine behavior</span></span>|  
|----------------------------------|--------------------------|  
|<span data-ttu-id="fef16-107">0</span><span class="sxs-lookup"><span data-stu-id="fef16-107">0</span></span>|<span data-ttu-id="fef16-108">Valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="fef16-108">Default value.</span></span> <span data-ttu-id="fef16-109">el motor de reglas sigue el modelo de BizTalk Server 2004, donde sólo se llama al método estático cuando se impone una instancia de la clase .NET.</span><span class="sxs-lookup"><span data-stu-id="fef16-109">The rule engine follows the BizTalk Server 2004 model, where the static method is called only when an instance of the .NET class is asserted.</span></span>|  
|<span data-ttu-id="fef16-110">1</span><span class="sxs-lookup"><span data-stu-id="fef16-110">1</span></span>|<span data-ttu-id="fef16-111">No se necesita una instancia del objeto.</span><span class="sxs-lookup"><span data-stu-id="fef16-111">An object instance is not required.</span></span> <span data-ttu-id="fef16-112">Se llama al método estático cuando se evalúa o ejecuta la regla.</span><span class="sxs-lookup"><span data-stu-id="fef16-112">The static method is called when the rule is evaluated or executed.</span></span>|  
|<span data-ttu-id="fef16-113">2</span><span class="sxs-lookup"><span data-stu-id="fef16-113">2</span></span>|<span data-ttu-id="fef16-114">No se necesita una instancia del objeto.</span><span class="sxs-lookup"><span data-stu-id="fef16-114">An object instance is not required.</span></span> <span data-ttu-id="fef16-115">Se llama al método estático en el momento de traducción de la directiva si todos los parámetros son constantes.</span><span class="sxs-lookup"><span data-stu-id="fef16-115">The static method is called at the policy translation time if all parameters are constant.</span></span> <span data-ttu-id="fef16-116">Esto supone una optimización del rendimiento porque se llama al método estático sólo una vez incluso aunque se use en varias reglas en condiciones.</span><span class="sxs-lookup"><span data-stu-id="fef16-116">This is a performance optimization because the static method is called only once even though it is used in multiple rules in conditions.</span></span> <span data-ttu-id="fef16-117">Tenga en cuenta que los métodos estáticos usados como acciones no se ejecutarán en el momento de traducción pero es posible que se ejecuten los métodos estáticos que se usen como parámetros.</span><span class="sxs-lookup"><span data-stu-id="fef16-117">Note that static methods used as actions will not be executed at the translation time, but static methods used as parameters may be executed.</span></span>|  
  
## <a name="adding-and-changing-the-staticsupport-registry-key"></a><span data-ttu-id="fef16-118">Agregar y cambiar la clave de Registro StaticSupport</span><span class="sxs-lookup"><span data-stu-id="fef16-118">Adding and Changing the StaticSupport Registry Key</span></span>  
 <span data-ttu-id="fef16-119">Si no ve el **StaticSupport** clave del registro bajo **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**, debería agregarla mediante los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="fef16-119">If you do not see the **StaticSupport** registry key under **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**, you should add it by performing the following steps.</span></span>  
  
 <span data-ttu-id="fef16-120">**Para agregar la clave de registro StaticSupport**</span><span class="sxs-lookup"><span data-stu-id="fef16-120">**To add the StaticSupport registry key**</span></span>  
  
1.  <span data-ttu-id="fef16-121">Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **RegEdit**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fef16-121">Click **Start**, click **Run**, type **RegEdit**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="fef16-122">Expanda **HKEY_LOCAL_MACHINE**, expanda **Software**, expanda **Microsoft**, expanda **BusinessRules**y, a continuación, seleccione **3.0**.</span><span class="sxs-lookup"><span data-stu-id="fef16-122">Expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Microsoft**, expand **BusinessRules**, and then select **3.0**.</span></span>  
  
3.  <span data-ttu-id="fef16-123">En el panel derecho, haga clic en, seleccione **New**y, a continuación, haga clic en **valor DWORD**.</span><span class="sxs-lookup"><span data-stu-id="fef16-123">In the right pane, right-click, point to **New**, and then click **DWORD value**.</span></span>  
  
4.  <span data-ttu-id="fef16-124">Para **nombre**, tipo **StaticSupport**.</span><span class="sxs-lookup"><span data-stu-id="fef16-124">For **Name**, type **StaticSupport**.</span></span>  
  
 <span data-ttu-id="fef16-125">Si el **StaticSupport** clave del registro ya existe y tiene que cambiar su valor, realice los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="fef16-125">If the **StaticSupport** registry key already exists, and you need to change its value, perform the following steps.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fef16-126">Si BizTalk está instalado en un equipo de 64 bits, puede agregar **StaticSupport** clave del registro con cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="fef16-126">If BizTalk is installed on a 64-bit machine, then you can add **StaticSupport** registry key using either of the following options:</span></span>  
>   
>  -   <span data-ttu-id="fef16-127">Busque en HKLM\Software\Wow6432Node\Microsoft\BusinessRules\3.0.</span><span class="sxs-lookup"><span data-stu-id="fef16-127">You need to look under HKLM\Software\Wow6432Node\Microsoft\BusinessRules\3.0.</span></span> <span data-ttu-id="fef16-128">Si existe esta clave, puede agregar **StaticSupport** aquí.</span><span class="sxs-lookup"><span data-stu-id="fef16-128">If this key exists, then you can add **StaticSupport** here.</span></span>  
> -   <span data-ttu-id="fef16-129">Otra opción consiste en colocar **StaticSupport** en el **BTNTsvc [64] exe. config** archivo, esta configuración reemplaza el contenido en el registro.</span><span class="sxs-lookup"><span data-stu-id="fef16-129">Another option is to put **StaticSupport** in the **BTNTsvc[64].exe.config** file, as any settings here override what's in the Registry.</span></span>  <span data-ttu-id="fef16-130">Además, también se puede argumentar que esta opción es preferible, ya que aísla el cambio del comportamiento predeterminado solo en BizTalk, mientras que la configuración del Registro se aplica a todo el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="fef16-130">Further, one can also make the argument that this option is preferred since it isolates the change in default behavior to BizTalk only, whereas Registry settings are global to the Operating System.</span></span>  
  
 <span data-ttu-id="fef16-131">**Para cambiar el valor de la clave de registro StaticSupport**</span><span class="sxs-lookup"><span data-stu-id="fef16-131">**To change the value of the StaticSupport registry key**</span></span>  
  
1.  <span data-ttu-id="fef16-132">Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **RegEdit**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fef16-132">Click **Start**, click **Run**, type **RegEdit**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="fef16-133">Expanda **HKEY_LOCAL_MACHINE**, expanda **Software**, expanda **Microsoft**, expanda **BusinessRules**y, a continuación, expanda **3.0**.</span><span class="sxs-lookup"><span data-stu-id="fef16-133">Expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Microsoft**, expand **BusinessRules**, and then expand **3.0**.</span></span>  
  
3.  <span data-ttu-id="fef16-134">Haga doble clic en el **StaticSupport** registro de clave, o haga clic en él y, a continuación, haga clic en **modificar**.</span><span class="sxs-lookup"><span data-stu-id="fef16-134">Double-click the **StaticSupport** registry key, or right-click it and then click **Modify**.</span></span>