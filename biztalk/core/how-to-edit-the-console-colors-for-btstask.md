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
# <a name="how-to-edit-the-console-colors-for-btstask"></a>Cómo editar los colores de la consola para BTSTask
En este tema se describe cómo editar los colores de primer plano que BTSTask muestra en la consola. Si el color de fondo de la consola es blanco, tendrá dificultad en lee el resultado predeterminado de la consola de BTSTask y tendrá que modificar los colores de primer plano de la consola.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento de este tema, debe tener permisos de lectura y escritura en el archivo BTSTask.exe.config que se encuentra en la carpeta de instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-edit-the-console-foreground-colors-for-btstask"></a>Para editar los colores de primer plano de la consola para BTSTask  
  
1. En el equipo en el que desea ejecutar BTSTask, abra BTSTask.exe.config en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], o en un editor XML o de textos. Este archivo se encuentra en la carpeta de instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
2. Edite los valores Console.ForegroundColor.Error, Console.ForegroundColor.Warning y Console.ForegroundColor.Info para las claves según los colores de primer plano de la consola que desea para mensajes de error, advertencias e información respectivamente y luego guarde el archivo. (Para monocromo, elimine estas tres entradas en vez de editar sus valores.)  
  
    Los valores disponibles para los colores de primer plano son los siguientes:  
  
    0: negro  
  
    1: azul oscuro  
  
    2: verde oscuro  
  
    3: cian oscuro  
  
    4: rojo oscuro  
  
    5: magenta oscuro  
  
    6: DarkYellow  
  
    7: gris  
  
    8: Grisoscuro  
  
    9: azul  
  
    10: verde  
  
    11: cian  
  
    12: rojo  
  
    13: magenta  
  
    14: amarillo  
  
    15: en blanco  
  
## <a name="see-also"></a>Vea también  
 [Referencia de línea de comandos de BTSTask](../core/btstask-command-line-reference.md)