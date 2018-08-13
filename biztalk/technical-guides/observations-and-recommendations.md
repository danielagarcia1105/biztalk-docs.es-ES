---
title: Observaciones y recomendaciones | Microsoft Docs
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
ms.openlocfilehash: bf134382be6086a1a3ab96fa649fa6cbb41d9bad
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980077"
---
# <a name="observations-and-recommendations"></a>Observaciones y recomendaciones
## <a name="test-results-summary"></a>Resumen de los resultados de pruebas  
 Se observaron los resultados para el escenario de mensajería para ser ~ 109,382,400 mensajes por día. Para el escenario de orquestación, los resultados indican que un único equipo que ejecuta BizTalk Server puede procesar hasta 58,752,000 mensajes por día. Estos resultados se obtuvieron en un entorno de recinto de seguridad mediante hardware de clase empresarial normal implementado para muchas soluciones de BizTalk Server. Por lo tanto, estos resultados indican el tipo de rendimiento de BizTalk Server del que se puede lograr con ningún código personalizado. Las soluciones de clientes a menudo implican los artefactos de BizTalk personalizada; en muchos casos, esto aumenta los requisitos de procesamiento que afecta a su vez al rendimiento. Siguiendo los consejos que se presentan en esta guía, especialmente la [optimizar las aplicaciones de BizTalk Server](../technical-guides/optimizing-biztalk-server-applications.md) sección, el impacto de la implementación personalizada se pueden minimizar los artefactos de BizTalk Server.  
  
 En la tabla siguiente proporciona un resumen de los resultados de pruebas para esta valoración del rendimiento.  
  
|Escenario|Mensajería (KPI de BizTalk – documentos procesados por segundo)|Mensajería (KPI de SQL: uso de procesador SQL)|Latencia de mensajería (segundos)|Orquestación (KPI de BizTalk – documentos procesados por segundo)|Orquestación (KPI de SQL: uso de procesador SQL)|Latencia de orquestación (segundos)|  
|--------------|----------------------------------------------------------------|-------------------------------------------------------|-----------------------------------|--------------------------------------------------------------------|-----------------------------------------------------------|---------------------------------------|  
|Un único equipo MessageBox 1 BizTalk Server|1266 documentos procesados por segundo|59% de uso de CPU de SQL|0.06|680 documentos procesados por segundo|66.5% de uso de CPU de SQL|0.067|  
|Solo equipos con BizTalk Server de cuadro de mensajes 2|1267 documentos procesados por segundo|59.8% de uso de CPU de SQL|0.057|686 documentos procesados por segundo|68.5% de uso de CPU de SQL|0.067|  
|3 equipos del cuadro de mensajes 1 BizTalk Server|2102 documentos procesados por segundo|41% de uso de CPU de SQL|0.077|974 documentos procesados por segundo|48% de uso de CPU de SQL|0.11|  
|3 equipos de BizTalk Server de cuadro de mensajes 2|2285 documentos procesados por segundo|58% de uso de CPU de SQL|0.041|1065 documentos procesados por segundo|65% de uso de CPU de SQL|0..69|  
|4 equipos a los cuadros de mensajes 1 BizTalk Server|2125 documentos procesados por segundo|30% de uso de CPU de SQL|0.078|979 documentos procesados por segundo|37% de uso de CPU de SQL|0.095|  
|4 equipos a los cuadros de mensajes 2 BizTalk Server|2790 documentos procesados por segundo|50% de utilización de CPU de SQL|0.052|1487 documentos procesados por segundo|63% de uso de CPU de SQL|0.15|  
|4 equipos a los cuadros de mensajes 3 BizTalk Server|2656 documentos procesados por segundo|58% de uso de CPU de SQL|0.074|1388 documentos procesados por segundo|65% de uso de CPU de SQL|0.15|  
  
## <a name="comparison-of-performance-statistics-with-biztalk-server-2009"></a>Comparación de las estadísticas de rendimiento con BizTalk Server 2009  
 En la tabla siguiente se muestra una comparación de las estadísticas de rendimiento entre BizTalk Server 2009 y BizTalk Server 2010. Las estadísticas de rendimiento de BizTalk Server 2009 que aparece en esta tabla son de la Guía de optimización y rendimiento de BizTalk Server 2009.  
  
|Escenario|BizTalk Server 2009<br /> Máximo rendimiento sostenible (MST) de mensajes/seg.|BizTalk Server 2009<br />Número de servidores de BizTalk necesarios|BizTalk Server 2010<br />Máximo rendimiento sostenible (MST) de mensajes/seg.|BizTalk Server 2010<br />Número de servidores de BizTalk necesarios|% De diferencia de BizTalk Server 2010 desde BizTalk Server 2009|  
|--------------|----------------------------------------------------------------------------|-----------------------------------------------------------|---------------------------------------------------------------------------|-----------------------------------------------------------|---------------------------------------------------------------|  
|Mensajería - único cuadro de mensajes|1291|2|1266|1|98.06%|  
|Orquestación - cuadro de mensaje único|676|2|680|1|100.59%|  
|Mensajería - 3 cuadros de mensajes|2103|3|2285|2 (2102/s con 1 BTS)|108.65%|  
|Mensajería - 4 cuadros de mensajes|No aplicable|No aplicable|2790|2|No aplicable|  
|Orquestación - 3 cuadros de mensajes|1005|4|1065|2 (974/s con 1 BTS)|105.97%|  
|Orquestación - 4 cuadros de mensajes|No aplicable|No aplicable|1487|2|No aplicable|  
  
 En nuestro entorno de laboratorio, cuando se usa cuatro bases de datos de cuadro de mensajes, los resultados de rendimiento sostenible máximo fueron los siguientes:  
  
- Escenario de mensajería, 2790 documentos por segundo.  
  
- Escenario de orquestación, 1487 documentos por segundo.  
  
  **Consideraciones acerca del mensaje** mientras que BizTalk Server no impone ninguna restricción sobre el tamaño del mensaje, las pruebas se ejecutó para BizTalk Server 2010 usan solo los mensajes de 2 KB y el tipo de adaptador WCF usado fue el adaptador WCF-NetTCP. Esto coincide con el tipo de adaptador y de tamaño de mensaje utilizado en las pruebas de la Guía de optimización de rendimiento de BizTalk Server 2009.  
  
  Los controladores para la mejora del rendimiento son:  
  
1.  **Los avances de hardware** -utilizados en nuestro laboratorio de equipos de SQL Server estaban 4 CPU, cuatro núcleos (16 núcleos), Intel Xeon E7330 a 2,40 GHz. En las pruebas de 2009, 4 CPU, se utilizaron cuatro núcleos (16 núcleos), Intel Xeon a 2,4 GHz.  
  
     Los equipos de BizTalk Server utilizados en nuestro laboratorio eran cuatro núcleos (8 núcleos), Nehalem Hyper-Threading (16 núcleos lógicos), Intel Xeon X 2 CPU 5570 @ 2,93 GHz. En las pruebas de 2009, 2 CPU, se utilizaron cuatro núcleos (8 núcleos), Intel Xeon 2,33 GHz.  
  
2.  **Mejora del motor de SQL Server** -se realizaron las pruebas en 2009 en SQL Server 2008, mientras que las pruebas se realizaron con SQL Server 2008 R2, como la plataforma de base de datos subyacente.  
  
## <a name="recommendations-for-scaling-the-biztalk-server-and-sql-server-tiers"></a>Recomendaciones para escalar los niveles de servidor BizTalk Server y SQL Server  
 Con estos resultados, el equipo del producto BizTalk Server era capaz de demostrar que un solo equipo de BizTalk Server y un único equipo de SQL Server pueden admitir más 109 millones de mensajes en un escenario de mensajería y orquestaciones de 58 millones durante un período de 24 horas. Al escalar los niveles de servidor BizTalk Server y SQL para la configuración óptima disponible en nuestro entorno, pudimos procesar over241 millón de mensajes por día y las orquestaciones de más de 128 millones. Los resultados se realizaron en un entorno de recinto de seguridad mediante el uso de la clase de hardware implementado en muchas empresas. Como se indicó anteriormente, estos números representan el rendimiento realista de BizTalk Server que se pueden lograr con un entorno optimizado y ningún código personalizado.  Con el hardware adicional, es posible que incluso un mayor rendimiento se podría haber conseguido. Las soluciones de clientes a menudo implican artefactos de BizTalk personalizada que incurrir en los requisitos de procesamiento adicional, por lo tanto, aumentar la utilización de recursos y a su vez reduce el rendimiento general. Sin embargo, siguiendo los consejos que se describen en la guía, especialmente las recomendaciones de [optimizar las aplicaciones de BizTalk Server](../technical-guides/optimizing-biztalk-server-applications.md), se puede minimizar el impacto de esto.  
  
 Los resultados muestran que escalar horizontalmente el número de equipos con BizTalk Server es una estrategia eficaz de escalabilidad horizontal si el equipo del servidor SQL de cuadro de mensajes no es un cuello de botella. Después de un cierto punto que nuestros resultados indican que la adición de equipos de BizTalk Server se convierte en una técnica de escalada ineficaces porque hemos observado que se ha producido un punto de contención en las tablas dentro de la base de datos compartidas, lo que provocaba que el rendimiento a disminuir. Para maximizar los resultados que pueden obtenerse a partir de un grupo de BizTalk Server con una sola base de datos de cuadro de mensajes, debe aplicar la optimización descrita en [optimización del rendimiento de base de datos](../technical-guides/optimizing-database-performance.md). En concreto, debe asegurarse de que un subsistema de almacenamiento rápido se usa para el almacenamiento de SQL Server y que responden los discos lógicos que usa SQL Server para almacenar los archivos de base de datos de cuadro de mensajes en el menor tiempo posible. Un umbral usado para medir el rendimiento de lectura/escritura aceptable es 15 milisegundos; Normalmente se mide por el contador promedio Segundos de disco/lectura y promedio Contadores de segundos/escritura de disco que pueden encontrarse en el objeto de rendimiento de disco lógico. Una vez que se han aplicado todas las optimizaciones disponibles en el equipo de SQL Server que hospeda la base de datos de cuadro de mensajes, se pueden agregar bases de datos de cuadro de mensajes adicionales. También se deben aplicar las mismas técnicas de optimización que se aplicaron a la base de datos principal a las bases de datos secundaria. Se recomienda que siga las instrucciones de [escalar horizontalmente el nivel de SQL Server](http://go.microsoft.com/fwlink/?LinkID=158075) (http://go.microsoft.com/fwlink/?LinkID=158075) en la documentación de BizTalk Server.  
  
 Para obtener resultados óptimos, la pila completa de hardware y software debe ser de calidad adecuado y también está configurado correctamente. En primer lugar, debe ser adquirido incluidos hardware de buena calidad, pero sin limitarse a gigabit redes rápidas almacenamiento (SAN o discos locales de SQL de 15 K) y los equipos modernos que tienen varias CPU con varios núcleos por CPU. El equipo de SQL Server debe estar dedicado a procesamiento solo BizTalk Server. Cuando se ejecuta en un único equipo de SQL Server, se recomienda que se crean dos instancias de SQL, una para BizTalk MessageBox y otra para todas las demás bases de datos. Esto permite la configuración de toda la instancia que se configurará para un rendimiento óptimo en el cuadro de mensajes. Las optimizaciones recomendadas en [optimización del rendimiento de](../technical-guides/optimizing-performance.md) debe aplicarse paso a paso en el siguiente orden: [optimizar el rendimiento del sistema operativo](../technical-guides/optimizing-operating-system-performance.md), [optimización de red Rendimiento](../technical-guides/optimizing-network-performance.md), [Optimizations2 de base de datos de configuración previa](../technical-guides/pre-configuration-database-optimizations2.md), [configuración posterior a la base de datos Optimizations2](../technical-guides/post-configuration-database-optimizations2.md) y [generales de BizTalk Server Optimizations1](../technical-guides/general-biztalk-server-optimizations1.md). Creación de grupos de archivos dedicado para la base de datos de cuadro de mensajes y asignación de estos en los LUN de SAN, como se describe en [optimización de grupos de archivos para el Databases2](../technical-guides/optimizing-filegroups-for-the-databases2.md), puede proporcionar mejora considerable del rendimiento en función de su Configuración de SAN y el diseño LUN.  
  
 Para determinar cómo escalar el nivel de servidor BizTalk Server o SQL de manera eficaz, se recomienda que las pruebas de carga se realiza con mensajes que se aproxima a los datos de producción real. Antes de escalar el nivel de BizTalk Server, asegúrese de que SQL Server no es ya un cuello de botella, tal como se recomienda en [supervisión de rendimiento de SQL Server](../technical-guides/monitoring-sql-server-performance.md). Si SQL Server no es un cuello de botella y hay espacio en cabeza CPU en cualquiera de los equipos de BizTalk Server, es podrán que pueda mejorar el rendimiento modificando el diseño de la instancia de host. Es importante establecer cuatro o cinco indicadores de rendimiento clave (KPI), que sirven como puntos de comparación de alto nivel para todas las ejecuciones de prueba. Siguiendo este Consejo, será capaz de estimar rápidamente si un determinado cambio disminución del rendimiento general de la solución.  
  
 Antes de escalar horizontalmente el nivel de SQL Server, se aplican todas las optimizaciones en [optimización del rendimiento de base de datos](../technical-guides/optimizing-database-performance.md). Durante el transcurso de laboratorios de rendimiento de cliente, la observación estaba esa configuración de almacenamiento de discos en el cuadro de mensajes y las bases de datos TempDb en particular pueden proporcionar más 30 por ciento mejora del rendimiento. Cuando se escala a varias bases de datos de cuadro de mensajes, se utilizaron tres y cuatro bases de datos porque no hay pocas ventajas de rendimiento durante el escalado horizontal de una sola base de datos de cuadro de mensajes en dos bases de datos de cuadro de mensajes. Para obtener más información sobre el escalado horizontal del cuadro de mensajes de BizTalk Server, consulte [escalar horizontalmente el nivel de SQL Server](http://go.microsoft.com/fwlink/?LinkID=158075) (http://go.microsoft.com/fwlink/?LinkID=158075) en la documentación de BizTalk Server.  
  
## <a name="implemented-optimizations"></a>Optimizaciones implementadas  
 Esta sección proporciona una lista de comprobación de todas las optimizaciones que se aplicaron para los escenarios de prueba de laboratorio.  
  
> [!NOTE]  
>  Estos se deben probar con arreglo a los procedimientos de administración de cambios antes de aplicar esas opciones en el entorno de producción.  
  
 Aplicar las optimizaciones de una manera controlada y sistemática, aplicando un conjunto de optimizaciones, pruebas, a continuación, el impacto: dará como resultado la ventaja de rendimiento máximo. Aplicar optimizaciones sin comprobar periódicamente el impacto de las optimizaciones realmente puede producir una degradación del rendimiento de la solución.  
  
### <a name="checklists-of-optimizations-applied"></a>Listas de comprobación de optimizaciones aplicadas  
 **Plataforma y optimizaciones de red**  
  
|Optimization|Referencia|  
|------------------|---------------|  
|BIOS: Configurar opciones de rendimiento.|[Optimización del rendimiento del sistema operativo](../technical-guides/optimizing-operating-system-performance.md)|  
|Deshabilitar el análisis en tiempo real en los archivos de SQL Server.|[Optimización del rendimiento del sistema operativo](../technical-guides/optimizing-operating-system-performance.md)|  
|Habilitar el "alto rendimiento" Plan de energía en todos los equipos de BizTalk Server y SQL Server.|[Directrices generales para mejorar el rendimiento del sistema operativo](../technical-guides/general-guidelines-for-improving-operating-system-performance.md)|  
|Deshabilitar el Antivirus en equipos de todos los BizTalk Server y SQL Server.|[Directrices generales para mejorar el rendimiento del sistema operativo](../technical-guides/general-guidelines-for-improving-operating-system-performance.md)|  
  
 **Optimizaciones de SQL Server: General**  
  
|Optimization|Referencia|  
|------------------|---------------|  
|Establecer la unidad de asignación de archivos NTFS a 64 KB.|[Base de datos de configuración previa Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|Instalar SQL Server 2008 R2.|[Base de datos de configuración previa Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|Configurar SQL Server 2008 R2 datos recopilador/almacenamiento.|[Base de datos de configuración previa Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|Asegúrese de que los privilegios adecuados de Windows se han ampliado a las cuentas de servicio de SQL Server.|SQL Server 2008 R2: [configurar Windows de las cuentas de servicio](http://go.microsoft.com/fwlink/?LinkID=132144) (http://go.microsoft.com/fwlink/?LinkID=132144)|  
|Establezca la memoria de servidor mínima y máxima para SQL Server.|[Base de datos de configuración previa Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|Conceda el privilegio de Windows bloquear páginas en memoria a la cuenta que se usa para SQL Server.|[Base de datos de configuración previa Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|Cambiar tamaño previamente las bases de datos de BizTalk Server para el tamaño adecuado con varios archivos de datos...|[Configuración posterior a la base de datos Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)|  
|Configurar protocolos de cliente SQL Server.|[Solucionar problemas de SQL Server](http://go.microsoft.com/fwlink/?LinkID=154250) (http://go.microsoft.com/fwlink/?LinkID=154250)|  
|Dividir la base de datos tempdb en varios archivos de datos del mismo tamaño en cada instancia de SQL Server usados por BizTalk Server|[Base de datos de configuración previa Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|Establecer manualmente la afinidad de proceso de SQL Server|[Base de datos de configuración previa Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|Configurar MSDTC y deshabilitar el seguimiento de DTC|[Base de datos de configuración previa Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|Habilitar T1118 de marca de seguimiento como un parámetro de inicio para todas las instancias de SQL Server|[Base de datos de configuración previa Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
  
 **Optimizaciones de SQL Server: Bases de datos de BizTalk**  
  
|Optimization|Referencia|  
|------------------|---------------|  
|Establezca las bases de datos de crecimiento automático de BizTalk en un valor fijo y no un valor de porcentaje.|[Configuración posterior a la base de datos Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)|  
|Mover o dividir archivos de datos y de registro de base de datos de BizTalk para separar los LUN.|[Configuración posterior a la base de datos Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)|  
|Considere la posibilidad de establecer la opción de tabla 'text in row' en tablas de base de datos de cuadro de mensajes específicas|[Configuración posterior a la base de datos Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)|  
  
 **Optimizaciones de BizTalk**  
  
|Optimization|Referencia|  
|------------------|---------------|  
|Realizar un seguimiento en hosts independientes y dedicados, puertos de envío, orquestaciones y puertos de recepción independiente.|[Optimizations1 generales de BizTalk Server](../technical-guides/general-biztalk-server-optimizations1.md)|  
|Configurar intervalos de sondeo.|[Escenarios de baja latencia Optimizations2](../technical-guides/low-latency-scenario-optimizations2.md)|  
|Ajustar la propiedad de conexión máximo de archivo de configuración de BizTalk.|Sección "Aumentar el número de conexiones simultáneas de SOAP y HTTP permitido cambiando el valor del parámetro maxconnection" de [Optimizations1 General de servidor de BizTalk](../technical-guides/general-biztalk-server-optimizations1.md)|  
|Definir parámetros de hospedaje de CLR para cada instancia de host en cada nodo de servidor BizTalk Server:<br /><br /> Subprocesos de E/S máxima: 250<br /><br /> Subprocesos de trabajo máximo: 100<br /><br /> Subprocesos de E/S mínima: 25<br /><br /> Subprocesos de trabajo mínimo: 25|Sección "Definir valores de subprocesos para las instancias de host de BizTalk de hospedaje de CLR" de [Optimizations1 General de servidor de BizTalk](../technical-guides/general-biztalk-server-optimizations1.md)|  
|Aumente los mensajes en curso y el tamaño de la cola de mensajes interna a 10000.|[Escenarios de baja latencia Optimizations2](../technical-guides/low-latency-scenario-optimizations2.md)|  
|Deshabilitar el seguimiento de nivel de grupo de BizTalk Server.|[Optimizations1 generales de BizTalk Server](../technical-guides/general-biztalk-server-optimizations1.md)|  
|Administrar el número de solicitudes para las aplicaciones Web de ASP.NET 4 que pueden hospedar aisladas ubicaciones recibidas, servicios de back-end Web y servicios WCF en IIS 7.5 e IIS 7.0 que se ejecuta en modo integrado que se ejecutan concurrentemente|[Optimizations1 generales de BizTalk Server](../technical-guides/general-biztalk-server-optimizations1.md)|  
|Deshabilitar la limitación de host de BizTalk Server|[Optimizations1 generales de BizTalk Server](../technical-guides/general-biztalk-server-optimizations1.md)|  
|Configurar MSDTC y deshabilitar el seguimiento de DTC|[Optimizations1 generales de BizTalk Server](../technical-guides/general-biztalk-server-optimizations1.md)|  
  
 **Optimizaciones de configuración de WCF**  
  
|Optimization|Referencia|  
|------------------|---------------|  
|Para cada servicio WCF, aplicar el comportamiento del servicio serviceThrottling y establecer **maxConcurrentCalls** y **maxConcurrentSessions** a 200.|[Optimización del rendimiento del adaptador de WCF de BizTalk Server](../technical-guides/optimizing-biztalk-server-wcf-adapter-performance.md)|  
|Configurar el uso del comportamiento serviceThrottling en el archivo de configuración del servicio WCF back-end.|[Optimización del rendimiento del servicio web WCF](../technical-guides/optimizing-wcf-web-service-performance.md)|  
  
## <a name="see-also"></a>Vea también  
 [Escalado de un entorno de producción de BizTalk Server](../technical-guides/scaling-a-production-biztalk-server-environment.md)