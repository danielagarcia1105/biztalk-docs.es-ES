---
title: Página informes del portal | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51d793cc-dcea-4c29-883b-a5045d39d4f6
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a487f30fc4ca9897cfd1dc4642c26a2e5f36fd7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016775"
---
# <a name="portal-reports-page"></a>Página Informes del portal
La página de los informes del Portal, que se muestra en la figura 1 muestra los gráficos siguientes:  

- **Número de error por aplicación**. Esta opción muestra una vista agregada de todos los errores generados para un conjunto de aplicaciones especificado durante un tiempo especificado.  

- **Recuento de errores por tipo de Error**. Esta opción muestra una vista agregada de todos los errores por tipo de error especificado generado para un conjunto de aplicaciones especificado durante un tiempo especificado.  

- **Recuento de errores de tiempo**. Esta opción muestra el recuento de errores durante un período determinado para un conjunto de aplicaciones especificado. Puede seleccionar una aplicación para mostrar un gráfico de tendencias que muestra el número de errores con el tiempo para servicios específicos dentro de la aplicación.  

- **Número de alertas por aplicación**. Esta opción muestra una vista agregada de todas las alertas generadas para un conjunto de aplicaciones especificado durante un tiempo especificado.  

- **Reenvíos en el tiempo**. Esta opción muestra el recuento de reenvíos de mensajes con errores durante un período determinado para un conjunto de aplicaciones especificado.  

- **Las suscripciones de alerta con el tiempo**. Esta opción muestra el recuento de suscripciones de alerta durante un período determinado para un conjunto de aplicaciones especificado.  

  ![Página informes del portal](../esb-toolkit/media/portalreportspage.gif "PortalReportsPage")  

  **Figura 1**  

  **La página de los informes del Portal de administración de ESB**  

  En la lista siguiente se explica cómo puede usar las características de la página de Portal de administración de ESB de nueva entrada de registro:  

- Haga clic en el **SelectApplications** vincular por encima del primer gráfico y, a continuación, active o desactive las casillas de verificación en la lista de aplicaciones instaladas de Microsoft BizTalk Server que aparece. También puede usar los vínculos que aparecen seleccionar todas o ninguna de las aplicaciones. Haga clic en **guardar** para mostrar la información de las aplicaciones seleccionadas, o haga clic en **cancelar** para abandonar los cambios.  

- Use la lista desplegable situada encima del primer gráfico para seleccionar el intervalo durante el que desea que los gráficos para mostrar los datos. Puede elegir incluir datos de los anteriores **hora, día, semana, mes, trimestre, año,** o **todas**.  

- Haga clic en uno de los gráficos en la página para mostrar un desglose de los datos de servicio dentro de la aplicación. Según el gráfico seleccionado, se muestra una línea de tendencia o de recuento de errores individuales, las alertas, tipos de errores, reenvíos o suscripciones de alerta para cada servicio.  

- Haga clic en el nombre de un servicio en este gráfico para mostrar una tabla que enumera todos los errores, las alertas, tipos de error, reenvíos o suscripciones de alerta para el servicio seleccionado.  

- Haga clic en **exportar a Excel** para descargar la lista de suscripciones en un formato que puede ver en Microsoft Excel.
