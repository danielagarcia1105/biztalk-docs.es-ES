---
title: 'Paso 2: Configurar el controlador de pruebas de carga y de los equipos agente | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e9d937ac-55d8-48fa-bba2-3efe151587b8
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f931a05796856816e19b53ff5cba9f53b48c3e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-configure-load-test-controller-and-agent-computers"></a>Paso 2: Configurar el controlador de pruebas de carga y equipos de agente
Edición Visual Studio 2010 Ultimate puede generar carga simular hasta 250 usuarios virtuales en una serie de pruebas de carga local. Para simular más de 250 usuarios virtuales o para iniciar la prueba desde un equipo remoto equipo requiere Visual Studio Load Test Virtual usuario Pack 2010.  
  
 Todas las pruebas de carga realizadas para esta guía se inició desde dos equipos:  
  
-   Un equipo que ejecuta como un controlador de pruebas de carga y un agente de prueba de carga.  
  
-   Otro equipo que ejecute como sólo un agente de prueba de carga.  
  
 Resultados de pruebas se almacenan en un repositorio de resultados de pruebas de carga remoto en una base de datos de SQL Server 2008 R2.  
  
 Para obtener más información sobre el uso de controladores de pruebas y agentes de prueba para distribuir las pruebas de carga entre varias máquinas de pruebas, vea [distribuir cargar pruebas en varias pruebas máquinas usando controladores de pruebas y agentes de prueba](http://go.microsoft.com/fwlink/?LinkId=208406) (http:// ¿go.Microsoft.com/fwlink/? LinkId = 208406).  
  
## <a name="install-and-configure-the-load-test-controller-and-load-test-agents"></a>Instalar y configurar la carga de los agentes de prueba de carga y el controlador de pruebas  
 Para instalar y configurar el controlador de pruebas de carga y agentes de prueba de carga, consulte las secciones siguientes en el tema [instalar y configurar los agentes de Visual Studio y prueba y controladores de compilación](http://go.microsoft.com/fwlink/?LinkId=208455) (http://go.microsoft.com/fwlink/?LinkId=208455):  
  
-   Para configurar un controlador de pruebas, siga los procedimientos descritos en la [instalar un controlador de pruebas](http://go.microsoft.com/fwlink/?LinkId=208454) sección (http://go.microsoft.com/fwlink/?LinkId=208454).  
  
-   Para configurar agentes de prueba, siga los procedimientos descritos en la [instalar un agente de prueba](http://go.microsoft.com/fwlink/?LinkId=208456) sección (http://go.microsoft.com/fwlink/?LinkId=208456).