---
title: 'Paso 2: Configurar el controlador de pruebas de carga y de los equipos agente | Documentos de Microsoft'
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
ms.openlocfilehash: 75a659d533b68cf525bcd782a2dadce72a6ebb0b
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014091"
---
# <a name="step-2-configure-load-test-controller-and-agent-computers"></a>Paso 2: Configurar el controlador de pruebas de carga y equipos de agente

## <a name="overview"></a>Información general
Visual Studio puede generar carga simular hasta 250 usuarios virtuales en una serie de pruebas de carga local. Para simular más de 250 usuarios virtuales o para iniciar la prueba desde un equipo remoto equipo requiere Visual Studio carga prueba Virtual usuario.  
  
 Todas las pruebas de carga realizadas para esta guía se inició desde dos equipos:  
  
-   Un equipo que ejecuta como un controlador de pruebas de carga y un agente de prueba de carga.  
  
-   Otro equipo que ejecute como sólo un agente de prueba de carga.  
  
 Resultados de pruebas se almacenan en un repositorio de resultados de pruebas de carga remoto en una base de datos de SQL Server.  
  
 Para obtener más información sobre el uso de controladores de pruebas y agentes de prueba para distribuir las pruebas de carga entre varias máquinas de pruebas, vea [distribuir cargar pruebas en varias pruebas máquinas usando controladores de pruebas y agentes de pruebas](https://msdn.microsoft.com/library/dd728093.aspx).  
  
## <a name="install-and-configure-the-load-test-controller-and-load-test-agents"></a>Instalar y configurar la carga de los agentes de prueba de carga y el controlador de pruebas  
 Para instalar y configurar el controlador de pruebas de carga y agentes de prueba de carga, consulte [instalar y configurar agentes de prueba](https://docs.microsoft.com/visualstudio/test/lab-management/install-configure-test-agents).
