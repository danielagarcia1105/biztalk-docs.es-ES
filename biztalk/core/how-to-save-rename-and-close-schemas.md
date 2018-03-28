---
title: Cómo guardar, cambiar el nombre y cerrar esquemas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65e15d9e-40ae-4850-9c13-88033cb3b3bb
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a295bacf263e3ecad9a9aa081fb0d5d3be2f635
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-save-rename-and-close-schemas"></a><span data-ttu-id="49d5b-102">Cómo guardar, cambiar el nombre y cerrar esquemas</span><span class="sxs-lookup"><span data-stu-id="49d5b-102">How to Save, Rename, and Close Schemas</span></span>
<span data-ttu-id="49d5b-103">En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], los esquemas son archivos de lenguaje de definición de esquemas XML (XSD) y residen en el sistema de archivos con extensiones .xsd.</span><span class="sxs-lookup"><span data-stu-id="49d5b-103">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], schemas are XML Schema definition (XSD) language files and reside on the file system with .xsd extensions.</span></span> <span data-ttu-id="49d5b-104">Cuando utilice el Editor de BizTalk para desarrollar esquemas, tendrá que guardar y cerrar archivos de esquema como parte de la rutina; además, ocasionalmente, tendrá que cambiarles el nombre.</span><span class="sxs-lookup"><span data-stu-id="49d5b-104">When you use BizTalk Editor to develop schemas, you will routinely need to save and close schema files, and occasionally you may need to rename them.</span></span> <span data-ttu-id="49d5b-105">En este tema se describen los pasos necesarios para realizar estas operaciones básicas.</span><span class="sxs-lookup"><span data-stu-id="49d5b-105">This topic describes the steps required to perform these basic operations.</span></span>  
  
### <a name="to-save-a-schema"></a><span data-ttu-id="49d5b-106">Para guardar un esquema</span><span class="sxs-lookup"><span data-stu-id="49d5b-106">To save a schema</span></span>  
  
1.  <span data-ttu-id="49d5b-107">Si es necesario, active el Editor de BizTalk para guardar el esquema. Para ello, haga clic en la ficha correspondiente que se encuentra en la parte superior de la ventana de edición principal de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="49d5b-107">If necessary, activate BizTalk Editor for the schema to be saved by clicking the appropriate tab at the top of the main editing window in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="49d5b-108">En el **archivo** menú, haga clic en ** Guardar *\<nombre de esquema\>***.</span><span class="sxs-lookup"><span data-stu-id="49d5b-108">On the **File** menu, click **Save *\<Name of Schema\>***.</span></span>  
  
     <span data-ttu-id="49d5b-109">Si el esquema tiene cambios sin guardar, el nombre mostrado en la ficha en la parte superior de la ventana de edición principal no terminará con un asterisco (\*), que es el carácter utilizado para indicar que hay cambios sin guardar.</span><span class="sxs-lookup"><span data-stu-id="49d5b-109">If the schema had unsaved changes, its name as displayed on the tab at the top of the main editing window will no longer end with an asterisk (\*), which is used to indicate unsaved changes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49d5b-110">Puede guardar el esquema con un nombre nuevo, haga clic en **guardar *\<nombre de esquema\>* como** en el **archivo** menú.</span><span class="sxs-lookup"><span data-stu-id="49d5b-110">You can save the schema under a new name by clicking **Save *\<Name of Schema\>* As** on the **File** menu.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49d5b-111">Puede guardar el esquema como parte del proceso de guardar todos los elementos modificados en el proyecto, haga clic en **guardar todo** en el **archivo** menú.</span><span class="sxs-lookup"><span data-stu-id="49d5b-111">You can save the schema as part of saving all changed items in the project by clicking **Save All** on the **File** menu.</span></span>  
  
#### <a name="to-rename-a-schema"></a><span data-ttu-id="49d5b-112">Para cambiar el nombre de un esquema</span><span class="sxs-lookup"><span data-stu-id="49d5b-112">To rename a schema</span></span>  
  
1.  <span data-ttu-id="49d5b-113">En el Explorador de soluciones, haga clic en el esquema que desea cambiar y, a continuación, haga clic en **cambiar el nombre de**.</span><span class="sxs-lookup"><span data-stu-id="49d5b-113">In Solution Explorer, right-click the schema that you want to rename, and then click **Rename**.</span></span>  
  
2.  <span data-ttu-id="49d5b-114">En el cuadro de edición que aparece en la ubicación del esquema en el Explorador de soluciones, escriba el nuevo nombre del esquema o modifique el nombre existente y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="49d5b-114">In the editing box that appears in the location of the schema in Solution Explorer, type the new name for the schema, or alter its existing name, and then press ENTER.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49d5b-115">También puede cambiar la **nombre de tipo** del esquema cuando cambia el nombre.</span><span class="sxs-lookup"><span data-stu-id="49d5b-115">You may also want to change the **Type Name** of the schema when you rename.</span></span> <span data-ttu-id="49d5b-116">Cambia el **nombre de tipo** seleccionando el **esquema** en el Explorador de soluciones y escribiendo el nuevo nombre en el **nombre de tipo** en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="49d5b-116">You change the **Type Name** by selecting the **schema** in the solution explorer and entering the new name in the **Type Name** in the Properties window.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="49d5b-117">No debe cambiar el nombre de ningún esquema que utilice otro esquema.</span><span class="sxs-lookup"><span data-stu-id="49d5b-117">You should not rename any schema that is being used by another schema.</span></span> <span data-ttu-id="49d5b-118">Esto incluye los esquemas que se han incluido, importado o redefinido con otros esquemas, así como los esquemas de propiedades para los que se han establecido promociones.</span><span class="sxs-lookup"><span data-stu-id="49d5b-118">This includes schemas that have been included, imported, or redefined by other schemas, as well as property schemas for which promotions have already been established.</span></span> <span data-ttu-id="49d5b-119">Si lo hace, el esquema no encontrará el esquema cuyo nombre ha cambiado, porque el nombre que contiene ya no es exacto.</span><span class="sxs-lookup"><span data-stu-id="49d5b-119">If you do so, the schema that is being used will not be able to find the renamed schema because the name it contains will no longer be accurate.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49d5b-120">Algunos de los nombres que se eligen para los archivos del proyecto, como los archivos de esquema, pueden producir más adelante errores de compilación debido a conflictos con palabras reservadas del lenguaje C# y con nombres de tipos y espacios de nombres de .NET Framework (como "System").</span><span class="sxs-lookup"><span data-stu-id="49d5b-120">Certain name choices for project member files, such as schema files, can cause compilation errors later on due to conflicts with C# reserved words and.NET Framework type and namespace names (such as "System").</span></span> <span data-ttu-id="49d5b-121">Entre los ejemplos de esquemas se incluyen schema.xsd, XmlContent y RootNodes.</span><span class="sxs-lookup"><span data-stu-id="49d5b-121">Examples for schemas include schema.xsd, XmlContent, and RootNodes.</span></span> <span data-ttu-id="49d5b-122">Esto es porque el **nombre de tipo** valores predeterminados de la propiedad a la parte (no es una extensión) base de la **Filename** propiedad.</span><span class="sxs-lookup"><span data-stu-id="49d5b-122">This is because the **Type Name** property defaults to the base (non-extension) portion of the **Filename** property.</span></span> <span data-ttu-id="49d5b-123">Puede solucionar este tipo de error de compilación, cambie explícitamente el valor de la **nombre de tipo** propiedad a algo que no entra en conflicto.</span><span class="sxs-lookup"><span data-stu-id="49d5b-123">You can work around this type of compilation error by explicitly changing the value of the **Type Name** property to something that does not conflict.</span></span>  
  
#### <a name="to-close-a-schema"></a><span data-ttu-id="49d5b-124">Para cerrar un esquema</span><span class="sxs-lookup"><span data-stu-id="49d5b-124">To close a schema</span></span>  
  
1.  <span data-ttu-id="49d5b-125">Si es necesario, active el Editor de BizTalk para cerrar el esquema. Para ello, haga clic en la ficha correspondiente que se encuentra en la parte superior de la ventana de edición principal de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="49d5b-125">If necessary, activate BizTalk Editor for the schema to be closed by clicking the appropriate tab at the top of the main editing window in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="49d5b-126">En el menú **Archivo** , haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="49d5b-126">On the **File** menu, click **Close**.</span></span>  
  
     <span data-ttu-id="49d5b-127">Se cierra el Editor de BizTalk para el esquema que se ha cerrado.</span><span class="sxs-lookup"><span data-stu-id="49d5b-127">BizTalk Editor closes for the schema that has been closed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49d5b-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="49d5b-128">See Also</span></span>  
 [<span data-ttu-id="49d5b-129">Administración de esquemas en proyectos</span><span class="sxs-lookup"><span data-stu-id="49d5b-129">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)