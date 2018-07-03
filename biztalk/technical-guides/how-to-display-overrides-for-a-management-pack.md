---
title: Cómo mostrar invalidaciones para un módulo de administración | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8261a514-b4c4-4e6b-ac35-40a3e3e090e0
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc2a40fde14001668f94549240643160fd1af73a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979661"
---
# <a name="how-to-display-overrides-for-a-management-pack"></a>Cómo mostrar invalidaciones para un módulo de administración
Para mostrar invalidaciones para un módulo de administración, use el procedimiento siguiente.  
  
### <a name="to-display-overrides-for-a-management-pack"></a>Para mostrar invalidaciones para un módulo de administración  
  
1. En el servidor de administración, haga clic en **programas**y, a continuación, haga clic en **System Center**.  
  
2. Haga clic en **Shell de comandos**.  
  
3. En el Shell de comandos, escriba el siguiente comando:   
   `$mp = get-scommanagementpack -DisplayName "Operations Manager Internal Library"`   
   `$mp.GetOverrides()`  
  
4. Se crea un archivo CSV. El archivo .csv se puede abrir en Office Excel.  
  
   > [!NOTE]  
   >  En Office Excel, puede requerirse para especificar que el archivo .csv es un archivo de texto.  
  
   Por ejemplo, el comando siguiente muestra las anulaciones para uno de los módulos de administración principales:   
   `$mp = get-scommanagementpack -DisplayName "Contoso.BizTalk.Overrides.mp"`  
   `$mp.GetOverrides()`