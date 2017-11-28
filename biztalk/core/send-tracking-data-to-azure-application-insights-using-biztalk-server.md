---
title: Realizar un seguimiento de los datos para Application Insights o concentradores de eventos | Documentos de Microsoft
description: "Instalar feature pack para habilitar el análisis de datos de seguimiento con Azure Application Insights o concentradores de eventos de Azure en BizTalk Server"
ms.custom: fp1, fp2
ms.date: 11/16/2017
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
ms.openlocfilehash: 7a6fe0c50527f51b599bca5f51c7b8ed8fb7313e
ms.sourcegitcommit: f65e8ed2b8c18cded26b9d60868fb6a56bcc1205
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="send-biztalk-tracking-data-to-azure-application-insights-or-event-hubs"></a>Enviar datos a Azure Application Insights o concentradores de eventos de seguimiento de BizTalk

**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** , le permitirán procesar y enviar los datos de seguimiento a Azure Application Insights. 
          
**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2 de**:

* Visión de la aplicación es compatible con instancias predeterminadas SQL y las instancias con nombre de SQL
* Le permitirán procesar y enviar datos de seguimiento a los centros de eventos de Azure

Utilice estos servicios de Azure para realizar el seguimiento de las instancias de puertos de recepción, puertos de envío y orquestaciones.

## <a name="prerequisites"></a>Requisitos previos
* Crear una nueva instancia de [Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-create-new-resource). BizTalk Server utiliza el **clave de instrumentación** para autenticar.
* Crear un [concentrador de espacio de nombres y eventos de los centros de eventos de Azure](https://docs.microsoft.com/azure/event-hubs/event-hubs-create). BizTalk Server utiliza la directiva de nivel del centro de eventos o SAS (nivel de espacio de nombres) para autenticar.
* Instalar [Feature Pack 2 de](https://aka.ms/bts2016fp2) en el[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]

## <a name="enable-analytics-for-your-environment"></a>Habilitar el análisis de su entorno

1. Abra la **administración de BizTalk Server** de la consola, haga clic en el **grupo de BizTalk**y seleccione **configuración**. 
2. Comprobar **habilitar el análisis de nivel de grupo**.
3. Para el **tipo de destino**, seleccione **Application Insight** o **concentrador de eventos** en la lista.
    ![Habilitar el análisis de su entorno](../core/media/environmentsettingapplicationinishgt.PNG)

4. Para el **parámetros de conexión**, seleccione la **...**  botón, y **inicio de sesión** a su cuenta de Azure.  

    **Para Application Insights**  
    Seleccione el **suscripción**, **grupo de recursos**y la instancia de Application Insights.

    ![Habilitar el análisis de su entorno](../core/media/analytics-group-application-insights.png)

    **Para el concentrador de eventos**  
    Seleccione el **suscripción**, **grupo de recursos**, espacio de nombres del centro de eventos y centro de eventos. Para la autenticación, puede usar una firma de acceso (SAS) en el nivel de espacio de nombres, o la firma de entidad en el nivel del centro de eventos. Las claves disponibles son rellena automáticamente con los valores configurados previamente en [Azure](https://portal.azure.com).

    ![Habilitar el análisis de su entorno](../core/media/send-tracking-data-to-azure.png)

5. Seleccione **Aceptar** para guardar los cambios. 

Una vez habilitada, [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] está listo para transmitir datos al recurso de Azure. A continuación, habilitar el análisis en los puertos y orquestaciones. 

## <a name="enable-analytics-on-your-artifacts"></a>Habilitar el análisis en los artefactos

1. En administración de BizTalk Server, haga clic en un **puerto de recepción**, **puerto de envío** o **orquestación**y seleccione **seguimiento**.
2. En **análisis**, comprobar **Habilitar análisis**, de forma similar al siguiente. Esta opción inicia el seguimiento y transmitir datos desde el artefacto a los recursos de Azure.
    
    ![Datos de seguimiento para la orquestación](../core/media/orchestrationsettingsapplicationinsight.PNG)

3. Seleccione **Aceptar** para guardar los cambios.
4. Reinicie la instancia de host de seguimiento y confirme que se inicia la aplicación de BizTalk.

> [!TIP]
> Conectar los análisis de BizTalk Server con otros sistemas para obtener más información sobre los datos de las organizaciones.

## <a name="view-your-data"></a>Ver los datos

#### <a name="use-application-insights"></a>Use Application Insights
Una vez que los datos se envían a Application Insights, puede usar las herramientas de análisis dentro de Azure para crear consultas avanzadas y analizar los datos.

1. Inicie sesión en el [Portal de Azure](https://portal.azure.com).
2. Abra el recurso de Application Insights y seleccione **métricas explorador**.
3. Pueden mostrar gráficos vacíos. En un gráfico, seleccione **editar**. En **métricas**, seleccione **personalizado** para ver las propiedades de seguimiento disponibles. Seleccione algunas de las distintas opciones para ver los cambios en el gráfico: 

    ![Análisis de Azure](../core/media/azure-stream-metrics-custom.png)

4. Volver al recurso de Application Insights y seleccione **análisis**. En **uso**, seleccione **ejecutar**. Se ejecuta una consulta de ejemplo y los resultados se muestran en un gráfico.  

> [!TIP]
> Azure Application Insights es una herramienta eficaz. No hay recursos para ayudarle a escribir consultas en Application Insights en [funciones analíticas en Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)e incluso para empezar a trabajar en [¿qué es Application Insights?](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-overview).

#### <a name="use-event-hubs"></a>Usar centros de eventos
Una vez que los datos se envían a los centros de eventos, hay un par de maneras para ver los datos. Muchos usuarios de los centros de eventos están usando la captura de los centros de eventos para cargar datos de transmisión por secuencias en Azure. La intención es que centrarse en el procesamiento de datos, en lugar de captura de datos. [Captura de los centros de eventos](https://docs.microsoft.com/azure/event-hubs/event-hubs-capture-overview) explica cómo funciona y cómo se configura.

Otra opción es crear un puerto de recepción y ubicación de recepción mediante el adaptador de concentrador de eventos. A continuación, puede generar los datos en una carpeta. Esta idea puede ser la mejor si desea probar el escenario. [Adaptador de concentradores de eventos](event-hubs-adapter.md) enumera los pasos necesarios para recibir mensajes en BizTalk Server desde los centros de eventos.

## <a name="where-the-data-is-stored"></a>Donde se almacenan los datos

Los datos de seguimiento deben mostrarse con bastante rapidez (dentro de unos minutos) en los recursos de Azure. Si no es así, puede haber un problema con el host de seguimiento. En SQL Server, los datos de análisis se almacenan en la base de datos BizTalkMsgBoxDb en la TrackingData_2_*x* tablas. En SQL Server Management Studio, devuelve las 1000 filas superiores en estos cuatro tablas. Si los datos existe, el host de seguimiento no es mover los datos de la base de datos de BizTalkDTADb. 

Algunas soluciones posibles:

1. Reinicie el host de seguimiento.
2. Crear un host de seguimiento dedicado. Cuando se instala BizTalk Server, el seguimiento puede habilitarse en el **BizTalk Server Application 1** host. Normalmente, esta aplicación también se usa para procesar los mensajes. Crear un host de seguimiento dedicado siguiendo estos pasos: 

    1. En administración de BizTalk Server, abra las propiedades del host de BizTalk Server Application 1 y desactive la opción **Permitir seguimiento de Host**. Reinicie la instancia de host.

    2. Cree un nuevo host denominado **seguimiento**y compruebe **Permitir seguimiento de Host**. Crear una instancia de host e inícielo.

A continuación, volver a consultar las tablas de BizTalkMsgBoxDb TrackingData_2_x. Si las tablas están vacías, a continuación, los datos se ha movido y deben comenzar a mostrar en Application Insights.
    
## <a name="see-also"></a>Vea también
 [Instalar y configurar el Feature Pack](../core/configure-the-feature-pack.md)