---
title: "Cómo mostrar todas las reglas del módulo de administración | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7fdec550-6713-4f5f-8c04-d9218bf2df3c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08ec94eb3adb87bf6feaff032e00a61bc9b0fead
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-display-all-management-pack-rules"></a>Cómo mostrar todas las reglas del módulo de administración
Utilice el procedimiento siguiente para mostrar una lista de reglas para los módulos de administración que ha importado. La lista de reglas puede verse en Office Excel.  
  
### <a name="to-display-management-pack-rules"></a>Para mostrar las reglas del módulo de administración  
  
1.  En el servidor de administración, haga clic en **programas**y, a continuación, haga clic en **System Center**.  
  
2.  Haga clic en **Shell de comandos**.  
  
3.  En el Shell de comandos, escriba el siguiente comando:   
    `get-scommanagementpack -DisplayName "BizTalk Server Monitoring" | Get-SCOMRule | export-csv "c:\rules.csv"`  
  
4.  Se crea un archivo .csv. Puede abrir el archivo .csv en Office Excel.  
  
    > [!NOTE]  
    >  En Office Excel, puede ser necesario para especificar que el archivo .csv es un archivo de texto.