---
title: Cómo editar los colores de consola para BTSTask | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 725dcb7b-5a19-4166-9d1c-93f30ddca201
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f52c727d2606898084d6397e6eb1b96ddc129b6d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974877"
---
# <a name="how-to-edit-the-console-colors-for-btstask"></a><span data-ttu-id="71eaa-102">Cómo editar los colores de la consola para BTSTask</span><span class="sxs-lookup"><span data-stu-id="71eaa-102">How to Edit the Console Colors for BTSTask</span></span>
<span data-ttu-id="71eaa-103">En este tema se describe cómo editar los colores de primer plano que BTSTask muestra en la consola.</span><span class="sxs-lookup"><span data-stu-id="71eaa-103">This topic describes how to edit the foreground colors that BTSTask outputs to the console.</span></span> <span data-ttu-id="71eaa-104">Si el color de fondo de la consola es blanco, tendrá dificultad en lee el resultado predeterminado de la consola de BTSTask y tendrá que modificar los colores de primer plano de la consola.</span><span class="sxs-lookup"><span data-stu-id="71eaa-104">If your console background color is white, you will have difficulty reading the default BTSTask console output and will need to modify the console foreground colors.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="71eaa-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="71eaa-105">Prerequisites</span></span>  
 <span data-ttu-id="71eaa-106">Para realizar el procedimiento de este tema, debe tener permisos de lectura y escritura en el archivo BTSTask.exe.config que se encuentra en la carpeta de instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="71eaa-106">To perform the procedure in this topic, you must have Read/Write permissions on the BTSTask.exe.config file contained in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation folder.</span></span>  
  
### <a name="to-edit-the-console-foreground-colors-for-btstask"></a><span data-ttu-id="71eaa-107">Para editar los colores de primer plano de la consola para BTSTask</span><span class="sxs-lookup"><span data-stu-id="71eaa-107">To edit the console foreground colors for BTSTask</span></span>  
  
1. <span data-ttu-id="71eaa-108">En el equipo en el que desea ejecutar BTSTask, abra BTSTask.exe.config en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], o en un editor XML o de textos.</span><span class="sxs-lookup"><span data-stu-id="71eaa-108">On the computer where you want to run BTSTask, open BTSTask.exe.config in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] or a text or XML editor.</span></span> <span data-ttu-id="71eaa-109">Este archivo se encuentra en la carpeta de instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="71eaa-109">This file is located in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation folder.</span></span>  
  
2. <span data-ttu-id="71eaa-110">Edite los valores Console.ForegroundColor.Error, Console.ForegroundColor.Warning y Console.ForegroundColor.Info para las claves según los colores de primer plano de la consola que desea para mensajes de error, advertencias e información respectivamente y luego guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="71eaa-110">Edit the values for the Console.ForegroundColor.Error, Console.ForegroundColor.Warning, and Console.ForegroundColor.Info keys according to the console foreground colors that you want for error messages, warnings, and information, respectively, and then save the file.</span></span> <span data-ttu-id="71eaa-111">(Para monocromo, elimine estas tres entradas en vez de editar sus valores.)</span><span class="sxs-lookup"><span data-stu-id="71eaa-111">(For monochrome, delete these three entries, rather than editing their values.)</span></span>  
  
    <span data-ttu-id="71eaa-112">Los valores disponibles para los colores de primer plano son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="71eaa-112">The available values for foreground colors are as follows:</span></span>  
  
    <span data-ttu-id="71eaa-113">0: negro</span><span class="sxs-lookup"><span data-stu-id="71eaa-113">0: Black</span></span>  
  
    <span data-ttu-id="71eaa-114">1: azul oscuro</span><span class="sxs-lookup"><span data-stu-id="71eaa-114">1: DarkBlue</span></span>  
  
    <span data-ttu-id="71eaa-115">2: verde oscuro</span><span class="sxs-lookup"><span data-stu-id="71eaa-115">2: DarkGreen</span></span>  
  
    <span data-ttu-id="71eaa-116">3: cian oscuro</span><span class="sxs-lookup"><span data-stu-id="71eaa-116">3: DarkCyan</span></span>  
  
    <span data-ttu-id="71eaa-117">4: rojo oscuro</span><span class="sxs-lookup"><span data-stu-id="71eaa-117">4: DarkRed</span></span>  
  
    <span data-ttu-id="71eaa-118">5: magenta oscuro</span><span class="sxs-lookup"><span data-stu-id="71eaa-118">5: DarkMagenta</span></span>  
  
    <span data-ttu-id="71eaa-119">6: DarkYellow</span><span class="sxs-lookup"><span data-stu-id="71eaa-119">6: DarkYellow</span></span>  
  
    <span data-ttu-id="71eaa-120">7: gris</span><span class="sxs-lookup"><span data-stu-id="71eaa-120">7: Gray</span></span>  
  
    <span data-ttu-id="71eaa-121">8: Grisoscuro</span><span class="sxs-lookup"><span data-stu-id="71eaa-121">8: DarkGray</span></span>  
  
    <span data-ttu-id="71eaa-122">9: azul</span><span class="sxs-lookup"><span data-stu-id="71eaa-122">9: Blue</span></span>  
  
    <span data-ttu-id="71eaa-123">10: verde</span><span class="sxs-lookup"><span data-stu-id="71eaa-123">10: Green</span></span>  
  
    <span data-ttu-id="71eaa-124">11: cian</span><span class="sxs-lookup"><span data-stu-id="71eaa-124">11: Cyan</span></span>  
  
    <span data-ttu-id="71eaa-125">12: rojo</span><span class="sxs-lookup"><span data-stu-id="71eaa-125">12: Red</span></span>  
  
    <span data-ttu-id="71eaa-126">13: magenta</span><span class="sxs-lookup"><span data-stu-id="71eaa-126">13: Magenta</span></span>  
  
    <span data-ttu-id="71eaa-127">14: amarillo</span><span class="sxs-lookup"><span data-stu-id="71eaa-127">14: Yellow</span></span>  
  
    <span data-ttu-id="71eaa-128">15: en blanco</span><span class="sxs-lookup"><span data-stu-id="71eaa-128">15: White</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71eaa-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="71eaa-129">See Also</span></span>  
 [<span data-ttu-id="71eaa-130">Referencia de línea de comandos de BTSTask</span><span class="sxs-lookup"><span data-stu-id="71eaa-130">BTSTask Command-Line Reference</span></span>](../core/btstask-command-line-reference.md)