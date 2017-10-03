---
title: Enviar datos de seguimiento a Azure Application Insights mediante BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3ff6cb9-44d0-46cd-9b4f-a346365afb7b
caps.latest.revision: "10"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: f587c3049e191505c87ba456b5ddfd41011862c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="send-tracking-data-to-azure-application-insights-using-biztalk-server"></a>Enviar datos de seguimiento a Azure Application Insights con BizTalk Server
Enviar [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] datos de seguimiento para Inisights de aplicación de Azure. 

**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** , le permitirán procesar y enviar los datos de seguimiento a Azure Application Insights. Usar las características de Application Insights para realizar el seguimiento de las instancias de puertos de recepción, puertos de envío y orquestaciones.

## <a name="prerequisites"></a>Requisitos previos
* Crear una nueva instancia de [Application Insights](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource)
* Instalar [Feature Pack 1 de](https://www.microsoft.com/download/details.aspx?id=55100) en el[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]

## <a name="enable-analytics-for-your-environment"></a>Habilitar el análisis de su entorno

1. Abra la **administración de BizTalk Server** de la consola, expanda **de administración de BizTalk**, haga clic en el **grupo de BizTalk**y seleccione **configuración**. 
2. Comprobar **habilitar el análisis de nivel de grupo**.
3. Para el **tipo de destino**, seleccione **Application Insight** en la lista.
4. Para el **parámetros de conexión**, escriba la información de la aplicación  **[clave de instrumentación](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource)**  (disponible en el portal de Azure).

    La configuración del grupo un aspecto similar al siguiente: 

    ![Habilitar el análisis de su entorno](../core/media/environmentsettingapplicationinishgt.PNG)

5. Seleccione **Aceptar** para guardar los cambios. 

Una vez habilitada, [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] está listo para transmitir datos a Application Insights. A continuación, habilitar el análisis en los puertos y orquestaciones. 

## <a name="enable-analytics-on-your-artifacts"></a>Habilitar el análisis en los artefactos

1. En administración de BizTalk Server, haga clic en un **puerto de recepción**, **puerto de envío** o **orquestación**y seleccione **seguimiento**.
2. En **análisis**, comprobar **Habilitar análisis**. Esta opción inicia el seguimiento y transmitir datos desde el artefacto a Application Insights.

    La configuración del artefacto un aspecto similar al siguiente: 
    
    ![Datos de seguimiento para la orquestación](../core/media/orchestrationsettingsapplicationinsight.PNG)

3. Seleccione **Aceptar** para guardar los cambios.

A continuación, ejecute las consultas en Application Insights para ver los datos.  

> [!TIP]
> Conectar los análisis de BizTalk Server con otros sistemas para obtener más información sobre los datos de las organizaciones.

## <a name="run-queries-on-your-data"></a>Ejecutar consultas en los datos
Una vez que los datos se envían a Application Insights, puede usar las herramientas de análisis dentro de Azure para crear consultas avanzadas y analizar los datos.

1. Inicie sesión en el [Portal de Azure](https://portal.azure.com).
2. Abra el recurso de Application Insights y seleccione **análisis**.
3. Seleccione **uso**, y ejecute la consulta proporcionada.

    > [!TIP]
    > Obtener más información sobre cómo escribir consultas en Application Insights en [funciones analíticas en Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-analytics).
    
## <a name="see-also"></a>Vea también
 [Configurar el Feature Pack](../core/configure-the-feature-pack.md)