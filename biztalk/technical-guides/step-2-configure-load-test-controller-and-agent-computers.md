---
title: 'Paso 2: Configurar el controlador de pruebas de carga y los equipos agente | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9d937ac-55d8-48fa-bba2-3efe151587b8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b03a191269936311d04f7b773ed3159db66e34f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972453"
---
# <a name="step-2-configure-load-test-controller-and-agent-computers"></a>Paso 2: Configurar el controlador de pruebas de carga y equipos de agente

## <a name="overview"></a>Información general
Visual Studio puede generar carga simular hasta 250 usuarios virtuales en una serie de pruebas de carga local. Para simular más de 250 usuarios virtuales o para iniciar las pruebas desde un equipo remoto equipo requiere Visual Studio Load Test Virtual usuario.  
  
 Todas las pruebas de carga realizadas en esta guía se inició desde dos equipos:  
  
- Un equipo que se ejecuta como un controlador de pruebas de carga y un agente de prueba de carga.  
  
- Otro equipo que se ejecuta como un agente de prueba de carga solo.  
  
  Los resultados de pruebas se almacenan en un repositorio de resultados de pruebas de carga remoto en una base de datos de SQL Server.  
  
  Para obtener más información sobre cómo usar controladores de pruebas y agentes de prueba para distribuir las pruebas de carga entre varias máquinas de prueba, consulte [distribuir pruebas de carga a través de varias pruebas máquinas utilizando probar controladores y agentes de pruebas](https://msdn.microsoft.com/library/dd728093.aspx).  
  
## <a name="install-and-configure-the-load-test-controller-and-load-test-agents"></a>Instalar y configurar la carga de los agentes de prueba de carga y el controlador de pruebas  
 Para instalar y configurar el controlador de pruebas de carga y los agentes de prueba de carga, consulte [instalar y configurar agentes de prueba](https://docs.microsoft.com/visualstudio/test/lab-management/install-configure-test-agents).
