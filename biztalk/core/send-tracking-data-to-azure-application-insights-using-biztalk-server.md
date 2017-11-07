---
title: Enviar datos de seguimiento a Azure Application Insights | Documentos de Microsoft
description: "Instalar feature pack para habilitar el análisis de datos de seguimiento con Azure Application Insights en BizTalk Server"
ms.custom: fp1
ms.date: 11/06/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3ff6cb9-44d0-46cd-9b4f-a346365afb7b
caps.latest.revision: "10"
author: tordgladnordahl
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a65ffd2c5ee76d857effde6ab82dddf17b3de4b
ms.sourcegitcommit: 30189176c44873e3de42cc5f2b8951da51ffd251
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="send-tracking-data-to-azure-application-insights-using-biztalk-server"></a>Enviar datos de seguimiento a Azure Application Insights con BizTalk Server

**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** , le permitirán procesar y enviar los datos de seguimiento a Azure Application Insights. Usar las características de Application Insights para realizar el seguimiento de las instancias de puertos de recepción, puertos de envío y orquestaciones.
          
> [!IMPORTANT]
> Actualmente esta característica no funciona con las instancias con nombre de SQL.

## <a name="prerequisites"></a>Requisitos previos
* Crear una nueva instancia de [Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-create-new-resource). En sus propiedades, copie el **clave de instrumentación**. Péguelo en otro archivo, por lo que tiene listo. Usamos esta clave en BizTalk Server. 
* Instalar [Feature Pack 1 de](https://www.microsoft.com/download/details.aspx?id=55100) en el[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]

## <a name="enable-analytics-for-your-environment"></a>Habilitar el análisis de su entorno

1. Abra la **administración de BizTalk Server** de la consola, haga clic en el **grupo de BizTalk**y seleccione **configuración**. 
2. Comprobar **habilitar el análisis de nivel de grupo**.
3. Para el **tipo de destino**, seleccione **Application Insight** en la lista.
4. Para el **parámetros de conexión**, escriba la información de la aplicación  **[clave de instrumentación](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource)**  (disponible en el portal de Azure). La configuración del grupo un aspecto similar al siguiente: 

    ![Habilitar el análisis de su entorno](../core/media/environmentsettingapplicationinishgt.PNG)

5. Seleccione **Aceptar** para guardar los cambios. 

Una vez habilitada, [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] está listo para transmitir datos a Application Insights. A continuación, habilitar el análisis en los puertos y orquestaciones. 

## <a name="enable-analytics-on-your-artifacts"></a>Habilitar el análisis en los artefactos

1. En administración de BizTalk Server, haga clic en un **puerto de recepción**, **puerto de envío** o **orquestación**y seleccione **seguimiento**.
2. En **análisis**, comprobar **Habilitar análisis**, de forma similar al siguiente. Esta opción inicia el seguimiento y transmitir datos desde el artefacto a Application Insights.
    
    ![Datos de seguimiento para la orquestación](../core/media/orchestrationsettingsapplicationinsight.PNG)

3. Seleccione **Aceptar** para guardar los cambios.
4. Reinicie la instancia de host de seguimiento y confirme que se inicia la aplicación de BizTalk.

A continuación, ejecute las consultas en Application Insights para ver los datos.  

> [!TIP]
> Conectar los análisis de BizTalk Server con otros sistemas para obtener más información sobre los datos de las organizaciones.

## <a name="view-your-data"></a>Ver los datos
Una vez que los datos se envían a Application Insights, puede usar las herramientas de análisis dentro de Azure para crear consultas avanzadas y analizar los datos.

1. Inicie sesión en el [Portal de Azure](https://portal.azure.com).
2. Abra el recurso de Application Insights y seleccione **métricas explorador**.
3. Pueden mostrar gráficos vacíos. En un gráfico, seleccione **editar**. En **métricas**, seleccione **personalizado** para ver las propiedades de seguimiento disponibles. Seleccione algunas de las distintas opciones para ver los cambios en el gráfico: 

    ![Análisis de Azure](../core/media/azure-stream-metrics-custom.png)

4. Volver al recurso de Application Insights y seleccione **análisis**. En **uso**, seleccione **ejecutar**. Se ejecuta una consulta de ejemplo y los resultados se muestran en un gráfico.  

> [!TIP]
> Azure Application Insights es una herramienta eficaz. No hay recursos para ayudarle a escribir consultas en Application Insights en [funciones analíticas en Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)e incluso para empezar a trabajar en [¿qué es Application Insights?](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-overview).

## <a name="where-the-data-is-stored"></a>Donde se almacenan los datos

Los datos de seguimiento deben mostrarse con bastante rapidez (dentro de unos minutos) en Application Insights. Si no es así, puede haber un problema con el host de seguimiento. En SQL Server, los datos de análisis se almacenan en la base de datos BizTalkMsgBoxDb en la TrackingData_2_*x* tablas. En SQL Server Management Studio, devuelve las 1000 filas superiores en estos cuatro tablas. Si los datos existe, el host de seguimiento no es mover los datos de la base de datos de BizTalkDTADb. 

Algunas soluciones posibles:

1. Reinicie el host de seguimiento.
2. Crear un host de seguimiento dedicado. Cuando se instala BizTalk Server, el seguimiento puede habilitarse en el **BizTalk Server Application 1** host. Normalmente, esta aplicación también se usa para procesar los mensajes. Crear un host de seguimiento dedicado siguiendo estos pasos: 

    1. En administración de BizTalk Server, abra las propiedades del host de BizTalk Server Application 1 y desactive la opción **Permitir seguimiento de Host**. Reinicie la instancia de host.

    2. Cree un nuevo host denominado **seguimiento**y compruebe **Permitir seguimiento de Host**. Crear una instancia de host e inícielo.

A continuación, volver a consultar las tablas de BizTalkMsgBoxDb TrackingData_2_x. Si las tablas están vacías, a continuación, los datos se ha movido y deben comenzar a mostrar en Application Insights.
    
## <a name="see-also"></a>Vea también
 [Configurar el Feature Pack](../core/configure-the-feature-pack.md)