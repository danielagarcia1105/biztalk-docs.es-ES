---
title: "Cómo mostrar invalidaciones para un módulo de administración | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8261a514-b4c4-4e6b-ac35-40a3e3e090e0
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a28c4ab2ef8f82fdd770203816239ad78e74418e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-display-overrides-for-a-management-pack"></a>Cómo mostrar invalidaciones para un módulo de administración
Para mostrar invalidaciones para un módulo de administración, utilice el procedimiento siguiente.  
  
### <a name="to-display-overrides-for-a-management-pack"></a>Para mostrar invalidaciones para un módulo de administración  
  
1.  En el servidor de administración, haga clic en **programas**y, a continuación, haga clic en **System Center**.  
  
2.  Haga clic en **Shell de comandos**.  
  
3.  En el Shell de comandos, escriba el siguiente comando:   
    `$mp = get-scommanagementpack -DisplayName "Operations Manager Internal Library"`   
    `$mp.GetOverrides()`  
  
4.  Se crea un archivo .csv. El archivo .csv se puede abrir en Office Excel.  
  
    > [!NOTE]  
    >  En Office Excel, puede ser necesario para especificar que el archivo .csv es un archivo de texto.  
  
 Por ejemplo, el comando siguiente muestra las anulaciones para uno de los módulos de administración principales:   
`$mp = get-scommanagementpack -DisplayName "Contoso.BizTalk.Overrides.mp"`  
`$mp.GetOverrides()`