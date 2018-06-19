---
title: Observaciones y recomendaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88289080-1a59-4ffc-a0b2-312ec21940c2
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fba4c82725239bb8e37d8bf611dd721d1ee1514b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299708"
---
# <a name="observations-and-recommendations"></a>Observaciones y recomendaciones
## <a name="test-results-summary"></a>Resumen de resultados de pruebas  
 Los resultados para el escenario exclusivo de mensajería se observaron que ~ 109,382,400 mensajes al día. Para el escenario de orquestación, los resultados indican que un único equipo que ejecuta BizTalk Server puede procesar hasta 58,752,000 mensajes al día. Estos resultados se consiguieron en un entorno de espacio aislado con el hardware de clase empresarial normal implementado para muchas soluciones de BizTalk Server. Por lo tanto, estos resultados indican el tipo del rendimiento de BizTalk Server de la que se puede lograr con ningún código personalizado. Soluciones de cliente suelen implican desarrollados de forma personalizada artefactos de BizTalk; en muchos casos esto aumenta los requisitos de procesamiento que a su vez afecta al rendimiento. Siguiendo el Consejo presentado en esta guía, especialmente la [optimizar las aplicaciones de BizTalk Server](../technical-guides/optimizing-biztalk-server-applications.md) sección, el impacto de la implementación del servidor BizTalk Server desarrollados de forma personalizada se pueden minimizar los artefactos.  
  
 En la tabla siguiente proporciona un resumen de los resultados de pruebas para esta evaluación de rendimiento.  
  
|Escenario|Mensajería (KPI de BizTalk: documentos procesados por segundo)|Mensajería (KPI de SQL: uso de procesador SQL)|Latencia de mensajería (segundos)|Orquestación (KPI de BizTalk: documentos procesados por segundo)|Orquestación (KPI de SQL: uso de procesador SQL)|Latencia de orquestación (segundos)|  
|--------------|----------------------------------------------------------------|-------------------------------------------------------|-----------------------------------|--------------------------------------------------------------------|-----------------------------------------------------------|---------------------------------------|  
|Único equipo de servidor de BizTalk de 1 cuadro de mensajes|1266 documentos procesados por segundo|59% de uso de CPU de SQL|0.06|680 documentos procesados por segundo|66.5% de uso de CPU de SQL|0.067|  
|Solo equipos con BizTalk Server de cuadro de mensajes 2|1267 documentos procesados por segundo|59.8% de uso de CPU de SQL|0.057|686 documentos procesados por segundo|68.5% de uso de CPU de SQL|0.067|  
|3 de los equipos de servidor de BizTalk de 1 cuadro de mensajes|2102 documentos procesados por segundo|41% de uso de CPU de SQL|0.077|974 documentos procesados por segundo|48% de uso de CPU de SQL|0.11|  
|3 de los equipos de servidor BizTalk Server de cuadro de mensajes 2|2285 documentos procesados por segundo|58% de uso de CPU de SQL|0.041|1065 documentos procesados por segundo|65% de uso de CPU de SQL|0..69|  
|4 equipos con BizTalk Server de cuadros de mensajes 1|2125 documentos procesados por segundo|30% de uso de CPU de SQL|0.078|979 documentos procesados por segundo|El 37% de uso de CPU de SQL|0.095|  
|4 equipos con BizTalk Server de cuadros de mensajes 2|2790 documentos procesados por segundo|50% de utilización de CPU de SQL|0.052|1487 documentos procesados por segundo|63% de uso de CPU de SQL|0.15|  
|4 equipos con cuadros de mensajes 3 BizTalk Server|2656 documentos procesados por segundo|58% de uso de CPU de SQL|0.074|1388 documentos procesados por segundo|65% de uso de CPU de SQL|0.15|  
  
## <a name="comparison-of-performance-statistics-with-biztalk-server-2009"></a>Comparación de las estadísticas de rendimiento con BizTalk Server 2009  
 En la tabla siguiente se muestra una comparación de las estadísticas de rendimiento entre BizTalk Server 2009 y BizTalk Server 2010. Las estadísticas de rendimiento de BizTalk Server 2009 enumeradas en esta tabla son de la Guía de optimización y rendimiento de BizTalk Server 2009.  
  
|Escenario|BizTalk Server 2009<br /> Máximo rendimiento sostenible (MST) de mensajes/seg.|BizTalk Server 2009<br />Número de servidores de BizTalk necesarios|BizTalk Server 2010<br />Máximo rendimiento sostenible (MST) de mensajes/seg.|BizTalk Server 2010<br />Número de servidores de BizTalk necesarios|% De la diferencia de BizTalk Server 2010 desde BizTalk Server 2009|  
|--------------|----------------------------------------------------------------------------|-----------------------------------------------------------|---------------------------------------------------------------------------|-----------------------------------------------------------|---------------------------------------------------------------|  
|Mensajería - único cuadro de mensajes|1291|2|1266|1|98.06%|  
|Orquestación - cuadro de mensajes único|676|2|680|1|100.59%|  
|Mensajería - 3 cuadros de mensajes|2103|3|2285|2 (2102/s con 1 BTS)|108.65%|  
|Mensajería - 4 cuadros de mensajes|No aplicable|No aplicable|2790|2|No aplicable|  
|Orquestación - 3 cuadros de mensajes|1005|4|1065|2 (974/s con 1 BTS)|105.97%|  
|Orquestación - 4 cuadros de mensajes|No aplicable|No aplicable|1487|2|No aplicable|  
  
 En nuestro entorno de laboratorio, cuando se utiliza cuatro bases de datos de cuadro de mensajes, los resultados de rendimiento sostenible máximo fueron los siguientes:  
  
-   Para el escenario de mensajería, 2790 documentos por segundo.  
  
-   Para el escenario de orquestación, 1487 documentos por segundo.  
  
 **Consideraciones de mensaje** mientras que BizTalk Server no impone ninguna restricción sobre el tamaño del mensaje, las pruebas se ejecutaron para BizTalk Server 2010 usan solo los mensajes de 2 KB y el tipo de adaptador WCF usado era adaptador WCF-NetTCP. Esto coincide con el tipo de tamaño y el adaptador de mensaje utilizado en la prueba de la Guía de optimización de rendimiento de BizTalk Server 2009.  
  
 Los controladores para la mejora del rendimiento son:  
  
1.  **Los avances de hardware** -equipos de SQL Server utilizados en nuestro laboratorio eran 4 CPU, cuatro núcleos (16 núcleos), Intel Xeon E7330 @ 2,40 GHz. En las pruebas de 2009, 4 CPU, se utilizaron cuatro núcleos (16 núcleos), Intel Xeon 2,4 GHz.  
  
     Los equipos de BizTalk Server utilizados en nuestro laboratorio eran cuatro núcleos (8 núcleos), Nehalem Hyper-Threading (16 núcleos lógicos), Intel Xeon X 2 CPU 5570 @ 2,93 GHz. En las pruebas de 2009, 2 CPU, se utilizaron cuatro núcleos (8 núcleos), Intel Xeon 2,33 GHz.  
  
2.  **Mejora del motor de SQL Server** -se realizaron las pruebas en 2009 en SQL Server 2008, mientras que las pruebas se realizaron con SQL Server 2008 R2 como la plataforma de base de datos subyacente.  
  
## <a name="recommendations-for-scaling-the-biztalk-server-and-sql-server-tiers"></a>Recomendaciones para la ampliación de los niveles de servidor BizTalk Server y SQL Server  
 Con estos resultados, el equipo del producto BizTalk Server pudo demostrar que un solo equipo de BizTalk Server y un único equipo de SQL Server pueden admitir más de 109 millones de mensajes en un escenario de mensajería y orquestaciones de 58 millones durante un período de 24 horas. Ajustando la escala de los niveles de la configuración óptima disponible en nuestro entorno de BizTalk Server y SQL, pudimos procesar over241 millones mensajes al día y orquestaciones de más de 128 millones. Los resultados se han ejecutado en un entorno de espacio aislado con la clase de hardware implementado en muchas empresas. Como se mencionó anteriormente, estos números representan el rendimiento realista de BizTalk Server que se pueden lograr con ningún código personalizado y un entorno optimizado.  Hardware adicional, es posible que incluso un mayor rendimiento podría haberse obtenido. Soluciones de cliente suelen implican artefactos de BizTalk desarrollados de forma personalizada que incurren en requisitos de procesamiento adicional, por lo tanto, aumenta la utilización de recursos y a su vez reduce el rendimiento general. No obstante, siguiendo el Consejo descrito en la guía, especialmente las recomendaciones de [optimizar las aplicaciones de BizTalk Server](../technical-guides/optimizing-biztalk-server-applications.md), se puede minimizar el impacto de este.  
  
 Los resultados muestran que escalar horizontalmente el número de equipos con BizTalk Server es una estrategia eficaz de escalabilidad horizontal si el equipo del servidor de SQL de cuadro de mensajes no es un cuello de botella. Después de un determinado punto que nuestros resultados indican que la adición de equipos de servidor BizTalk Server se convierte en una técnica de escalabilidad horizontal ineficaces porque hemos observado que se ha producido un punto de contención en las tablas compartidas dentro de la base de datos de cuadro de mensajes, qué provocó el rendimiento disminuir. Para maximizar los resultados que se pueden obtener de un grupo de BizTalk Server con una sola base de datos de cuadro de mensajes, debe aplicar la optimización descrita en [optimizar el rendimiento de base de datos](../technical-guides/optimizing-database-performance.md). En concreto, debe asegurarse de que un subsistema de almacenamiento rápido se usa para el almacenamiento de SQL Server y que los discos lógicos que usa SQL Server para almacenar los archivos de base de datos de cuadro de mensajes se responden en el menor tiempo posible. Un umbral de uso frecuente para medir el rendimiento de lectura/escritura aceptable es 15 milisegundos; Normalmente esto se mide por el contador promedio En segundos/lectura y promedio Contadores de segundos/escritura de disco que se encuentra en el objeto de rendimiento de disco lógico. Una vez que se han aplicado todas las optimizaciones disponibles en el equipo de SQL Server que hospeda la base de datos de cuadro de mensajes, se pueden agregar bases de datos de cuadro de mensajes adicionales. Las mismas técnicas de optimización que se aplicaron a la base de datos de cuadro de mensajes principal también deben aplicarse a las bases de datos secundarias. Se recomienda que siga las instrucciones de [ajuste de escala en espera el nivel de SQL Server](http://go.microsoft.com/fwlink/?LinkID=158075) (http://go.microsoft.com/fwlink/?LinkID=158075) en la documentación de BizTalk Server.  
  
 Para obtener resultados óptimos, la pila completa de hardware y software debe ser de calidad adecuado y también está configurado correctamente. En primer lugar, debe ser adquirido incluidos hardware de buena calidad, pero sin limitarse a, gigabit red rápida almacenamiento (SAN o discos locales de SQL de 15 K) y los equipos modernos que tienen varias CPU con varios núcleos por CPU. El equipo de SQL Server debe estar dedicado a procesamiento solo BizTalk Server. Cuando se ejecuta un solo equipo de SQL Server, se recomienda que se crean dos instancias de SQL, uno para BizTalk MessageBox y otro para todas las demás bases de datos. Esto permite la configuración de toda la instancia se configuran para un rendimiento óptimo del cuadro de mensajes. Las optimizaciones se recomienda en [optimizar el rendimiento de](../technical-guides/optimizing-performance.md) debe aplicarse paso a paso en el siguiente orden: [optimizar el rendimiento del sistema operativo](../technical-guides/optimizing-operating-system-performance.md), [optimizar red Rendimiento](../technical-guides/optimizing-network-performance.md), [Optimizations2 de base de datos de configuración previa](../technical-guides/pre-configuration-database-optimizations2.md), [Optimizations2 de base de datos de configuración posteriores a la](../technical-guides/post-configuration-database-optimizations2.md) y [generales de BizTalk Server Optimizations1](../technical-guides/general-biztalk-server-optimizations1.md). Crear grupos de archivos dedicado para la base de datos de cuadro de mensajes y asignar estas a través de los LUN de SAN, como se describe en [optimizar los grupos de archivos para el Databases2](../technical-guides/optimizing-filegroups-for-the-databases2.md), pueden ofrecer una mejora considerable del rendimiento en función de su Configuración de SAN y el diseño LUN.  
  
 Para determinar eficazmente cómo escalar el nivel de servidor BizTalk Server o SQL, se recomienda que las pruebas de carga se realiza con mensajes que se aproxima a los datos de producción real. Antes de escalar el nivel de servidor BizTalk Server, asegúrese de que SQL Server no es ya un cuello de botella, tal como se recomienda en [supervisión de rendimiento de SQL Server](../technical-guides/monitoring-sql-server-performance.md). Si SQL Server no es un cuello de botella y hay espacio en cabeza CPU en cualquiera de los equipos de BizTalk Server, es posible que pueda mejorar el rendimiento modificando el diseño de la instancia de host. Es importante establecer cuatro o cinco indicadores de rendimiento clave (KPI), que se utilizan como puntos de comparación de alto nivel para todas las ejecuciones de pruebas. Siguiendo este Consejo, podrá analizar rápidamente si un cambio determinado disminución del rendimiento general de la solución.  
  
 Antes de escalar horizontalmente el nivel de SQL Server, se aplican todas las optimizaciones en [optimizar el rendimiento de base de datos](../technical-guides/optimizing-database-performance.md). En el transcurso de laboratorios de rendimiento de cliente, la observación era esa configuración de almacenamiento de discos en el cuadro de mensajes y las bases de datos TempDb en concreto pueden proporcionar más de 30 por ciento mejora del rendimiento. Cuando se escala a varias bases de datos de cuadro de mensajes, se utilizaron tres y cuatro bases de datos de cuadro de mensajes porque no hay muy pocas ventajas de rendimiento mientras se escala horizontalmente de una sola base de datos de cuadro de mensajes en dos bases de datos de cuadro de mensajes. Para obtener más información acerca de cómo escalar horizontalmente el cuadro de mensajes de BizTalk Server, vea [ajuste de escala en espera el nivel de SQL Server](http://go.microsoft.com/fwlink/?LinkID=158075) (http://go.microsoft.com/fwlink/?LinkID=158075) en la documentación de BizTalk Server.  
  
## <a name="implemented-optimizations"></a>Optimizaciones de implementada  
 Esta sección proporciona una lista de comprobación de todas las optimizaciones que se aplicaron para los escenarios de prueba de laboratorio.  
  
> [!NOTE]  
>  Estos se deben probar con arreglo a los procedimientos de administración de cambios antes de aplicar estos dentro de su entorno de producción.  
  
 Aplicar las optimizaciones de forma sistemática y controlada, al aplicar un conjunto de optimizaciones, a continuación, probar el impacto, dará como resultado la ventaja de rendimiento máximo. Aplicar optimizaciones sin probarla periódicamente el impacto de las optimizaciones realmente puede producir una degradación del rendimiento de la solución.  
  
### <a name="checklists-of-optimizations-applied"></a>Listas de comprobación de las optimizaciones que se aplica  
 **Plataforma y optimizaciones de red**  
  
|Optimization|Referencia|  
|------------------|---------------|  
|BIOS: Configurar opciones de rendimiento.|[Optimizar el rendimiento del sistema operativo](../technical-guides/optimizing-operating-system-performance.md)|  
|Deshabilite el examen en tiempo real en los archivos de SQL Server.|[Optimizar el rendimiento del sistema operativo](../technical-guides/optimizing-operating-system-performance.md)|  
|Habilitar el "alto rendimiento" Plan de energía en todos los equipos de BizTalk Server y SQL Server.|[Directrices generales para mejorar el rendimiento del sistema operativo](../technical-guides/general-guidelines-for-improving-operating-system-performance.md)|  
|Deshabilitar Antivirus en equipos de todo el servidor BizTalk Server y SQL Server.|[Directrices generales para mejorar el rendimiento del sistema operativo](../technical-guides/general-guidelines-for-improving-operating-system-performance.md)|  
  
 **Optimizaciones de SQL Server: General**  
  
|Optimization|Referencia|  
|------------------|---------------|  
|Establecer la unidad de asignación de archivo NTFS a 64 KB.|[Base de datos de configuración previa Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|Instalar SQL Server 2008 R2.|[Base de datos de configuración previa Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|Configurar SQL Server 2008 R2 datos recopilador/almacén.|[Base de datos de configuración previa Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|Asegúrese de que los privilegios adecuados de Windows se han ampliado a las cuentas de servicio de SQL Server.|SQL Server 2008 R2: [configuración de Windows, las cuentas de servicio](http://go.microsoft.com/fwlink/?LinkID=132144) (http://go.microsoft.com/fwlink/?LinkID=132144)|  
|Establecer la memoria de servidor mínima y máxima para SQL Server.|[Base de datos de configuración previa Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|Conceda el privilegio de Windows Lock Pages In Memory a la cuenta que se usa para SQL Server.|[Base de datos de configuración previa Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|Cambiar tamaño previamente las bases de datos de BizTalk Server al tamaño adecuado con varios archivos de datos...|[Configuración posterior a la base de datos Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)|  
|Configurar protocolos de cliente SQL Server.|[Solucionar problemas de SQL Server](http://go.microsoft.com/fwlink/?LinkID=154250) (http://go.microsoft.com/fwlink/?LinkID=154250)|  
|Dividir la base de datos tempdb en varios archivos de datos del mismo tamaño en cada instancia de SQL Server utilizado por BizTalk Server|[Base de datos de configuración previa Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|Establecer manualmente la afinidad de proceso de SQL Server|[Base de datos de configuración previa Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|Configurar MSDTC y deshabilitar el seguimiento de DTC|[Base de datos de configuración previa Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|Habilitar T1118 de marca de seguimiento como un parámetro de inicio para todas las instancias de SQL Server|[Base de datos de configuración previa Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
  
 **Optimizaciones de SQL Server: Bases de datos de BizTalk**  
  
|Optimization|Referencia|  
|------------------|---------------|  
|Establece las bases de datos de crecimiento automático de BizTalk en un valor fijo y no un valor de porcentaje.|[Configuración posterior a la base de datos Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)|  
|Mover o dividir archivos de datos y de registro de base de datos de BizTalk para separar los LUN.|[Configuración posterior a la base de datos Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)|  
|Considere la posibilidad de establecer la opción de tabla 'text in row' en tablas de base de datos de cuadro de mensajes específicas|[Configuración posterior a la base de datos Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)|  
  
 **Optimizaciones de BizTalk**  
  
|Optimization|Referencia|  
|------------------|---------------|  
|Independiente puertos de recepción, puertos de envío, orquestaciones y seguimiento en hosts independientes, dedicados.|[Optimizations1 generales de BizTalk Server](../technical-guides/general-biztalk-server-optimizations1.md)|  
|Configurar intervalos de sondeo.|[Escenario de baja latencia Optimizations2](../technical-guides/low-latency-scenario-optimizations2.md)|  
|Ajuste la propiedad de conexión máximo de archivo de configuración de BizTalk.|Sección "Aumentar el número de conexiones simultáneas de SOAP y HTTP permitido cambiando el valor para el parámetro maxconnection" de [General Optimizations1 de servidor de BizTalk](../technical-guides/general-biztalk-server-optimizations1.md)|  
|Definir parámetros de hospedaje de CLR para cada instancia de host en cada nodo de servidor BizTalk Server:<br /><br /> Subprocesos de E/S máxima: 250<br /><br /> Subprocesos de trabajo máximo: 100<br /><br /> Subprocesos de E/S mínima: 25<br /><br /> Subprocesos de trabajo mínimo: 25|Sección "Definir valores de subprocesos para instancias de host de BizTalk que hospedan el CLR" de [General Optimizations1 de servidor de BizTalk](../technical-guides/general-biztalk-server-optimizations1.md)|  
|Aumentar mensajes en curso y el tamaño de la cola de mensajes interna a 10000.|[Escenario de baja latencia Optimizations2](../technical-guides/low-latency-scenario-optimizations2.md)|  
|Deshabilitar el seguimiento de nivel de grupo de BizTalk Server.|[Optimizations1 generales de BizTalk Server](../technical-guides/general-biztalk-server-optimizations1.md)|  
|Administrar el número de solicitudes para las aplicaciones Web de ASP.NET 4 que pueden contener ubicaciones recibidos aislados, servicios Web de back-end y los servicios WCF en IIS 7.5 e IIS 7.0 que se ejecuta en modo integrado que se ejecutan concurrentemente|[Optimizations1 generales de BizTalk Server](../technical-guides/general-biztalk-server-optimizations1.md)|  
|Deshabilitar la limitación de host de BizTalk Server|[Optimizations1 generales de BizTalk Server](../technical-guides/general-biztalk-server-optimizations1.md)|  
|Configurar MSDTC y deshabilitar el seguimiento de DTC|[Optimizations1 generales de BizTalk Server](../technical-guides/general-biztalk-server-optimizations1.md)|  
  
 **Optimizaciones de configuración de WCF**  
  
|Optimization|Referencia|  
|------------------|---------------|  
|Para cada servicio WCF, aplicar el comportamiento del servicio serviceThrottling y establecer **maxConcurrentCalls** y **maxConcurrentSessions** a 200.|[Optimizar el rendimiento de adaptador WCF de BizTalk Server](../technical-guides/optimizing-biztalk-server-wcf-adapter-performance.md)|  
|Configurar el uso del comportamiento de serviceThrottling en el archivo de configuración del servicio WCF back-end.|[Optimizar el rendimiento del servicio Web WCF](../technical-guides/optimizing-wcf-web-service-performance.md)|  
  
## <a name="see-also"></a>Vea también  
 [Ajuste de escala en un entorno de BizTalk Server de producción](../technical-guides/scaling-a-production-biztalk-server-environment.md)