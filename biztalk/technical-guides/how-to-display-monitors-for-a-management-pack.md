---
title: Cómo mostrar monitores para un módulo de administración | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7c4d2b3-9c01-40f5-b983-bf29a3a5cacc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d561c7b49c47d59f7affccaaee582e26db500c09
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010277"
---
# <a name="how-to-display-monitors-for-a-management-pack"></a>Cómo mostrar monitores para un módulo de administración
Para mostrar una lista de salidas de un módulo de administración monitores e invalidaciones usando el Shell de comandos, utilice el procedimiento siguiente.  
  
### <a name="to-display-monitors-for-a-management-pack"></a>Para mostrar a monitores para un módulo de administración  
  
1. En el servidor de administración, haga clic en **programas**y, a continuación, haga clic en **System Center.**  
  
2. Haga clic en **Shell de comandos**.  
  
3. En el Shell de comandos, escriba el siguiente comando:   
   `get-scommanagementpack –DisplayName “DisplayName” | get-scommonitor | export.csv filename`  
  
4. Se crea un archivo CSV. El archivo .csv se puede abrir en Microsoft Office Excel.  
  
   > [!NOTE]  
   >  En Excel, puede requerirse para especificar que el archivo .csv es un archivo de texto.  
  
   Por ejemplo, el comando siguiente recupera los datos para los monitores asociados a uno de los módulos de administración principales:   
   `get-scommanagementpack -DisplayName "BizTalk Server Monitoring" | Get-ScomMonitor | export-csv "c:\monitors.csv"`