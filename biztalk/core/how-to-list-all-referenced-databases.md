---
title: Cómo enumerar todos los que hace referencia a las bases de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f6166dd-6228-45c2-98ef-4de2a4345189
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76a953933d72803b718353f7d0456317585b1458
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968477"
---
# <a name="how-to-list-all-referenced-databases"></a>Cómo enumerar todas las bases de datos a las que se hace referencia
Los administradores utilizan el **get-references** comando para enumerar todas las bases de datos de importación principal de BAM en otros servidores de BizTalk que se han recibido referencias a la base de datos local de importación principal de BAM.  
  
### <a name="to-list-all-referenced-databases"></a>Para enumerar todas las bases de datos a las que se hace referencia  
  
1. Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2. Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.  
  
3. Escriba lo siguiente en el símbolo del sistema de línea de comandos: **bm.exe get-references**. Presione **ENTRAR**.  
  
## <a name="see-also"></a>Vea también  
 [Utilidad de administración de BAM](../core/bam-management-utility.md)