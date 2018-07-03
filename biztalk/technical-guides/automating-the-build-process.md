---
title: Automatizar el proceso de compilación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 995dac20-82a1-46ed-b8a3-0aa6182cb821
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22752c413446c0964b8af11b76a2e262fdc40a2d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997733"
---
# <a name="automating-the-build-process"></a>Automatizar el proceso de compilación
Un proceso de compilación automatizado compila, implementa y, a continuación, ejecuta pruebas de comprobación de la compilación (BVT) en el código fuente más reciente para un proyecto a intervalos regulares, predeterminados. A continuación, un "informe de compilación", que detalla el éxito o error del proceso de compilación, se difunde a los participantes del proyecto. El informe de compilación se analiza para determinar qué áreas del proyecto necesitan atención y si el proyecto se debería deshacer para una compilación/versión anterior.  
  
 La potencia de un proceso de compilación automatizado es que puede programarse para ejecutarse durante "desactivar horas". De este modo, puede ayudar a garantizar la estabilidad del proyecto sin realizar ciclos directamente a la hora de desarrollo.   
 En este tema proporciona información general sobre el proceso de compilación, se describe cómo las pruebas de comprobación de compilación se integra en el proceso de compilación, se describe aspectos de las pruebas funcionales utilizado durante la prueba de comprobación de compilación y se proporciona información sobre la importancia de automatizar el proceso de compilación.  
  
## <a name="overview-of-the-build-process"></a>Información general del proceso de compilación  
 Antes de buscar en los detalles de las pruebas, es importante tener en cuenta el contexto de cómo se adapta las pruebas en el proceso de compilación general. Todos los grupos de productos de Microsoft funcionan de la filosofía que el proceso de compilación es el latido de cualquier proyecto de software. Este enfoque también se usa por muchos de los principales del mundo consulting las empresas que desarrollan soluciones de misión crítica encima de la pila de software de Microsoft. Sin un latido constante y una comprobación periódica del mismo, es imposible saber el estado del proyecto. Para asegurarse de que los grupos de productos tienen una información continua sobre el estado general del proyecto, el proceso de compilación se ejecuta a diario, normalmente a medianoche. Los pasos siguientes resumen un proceso de compilación automatizado típico:  
  
1.  Obtener la última compilación de código fuente desde el repositorio de código fuente.  
  
2.  Compile el código fuente.  
  
3.  Paquete de archivos binarios para la implementación – normalmente mediante scripts o archivos de Microsoft Windows Installer.  
  
4.  Implementar el proyecto en un servidor de prueba.  
  
5.  Ejecutar automáticamente un conjunto completo de pruebas de comprobación de la compilación (BVT).  
  
6.  Publicar un informe de compilación detalladas a los miembros del equipo del proyecto.  
  
> [!NOTE]  
>  BVT son pruebas funcionales que actúan sobre las características principales de la solución para probar su calidad.  Debe asegurarse de que sus pruebas de BVT son lo suficientemente exhaustivos para medir la calidad de compilación, pero lo suficientemente pequeño para ejecutar dentro del tiempo de compilación diaria asignado!  
  
> [!NOTE]  
>  También debe tratar la implementación, anular la implementación, configuración e instalación de secuencias de comandos o procesos como parte del proyecto de software con fines de prueba. Las operaciones de proyecto, así como la implementación y configuración del mismo, se deben probar.  
  
 Este proceso se realiza normalmente temprano aproximadamente 6 a. M., lo que permite a los primeros miembros del equipo empezar a trabajar en la compilación del nuevo día. Si una o varias de las pruebas de BVT de la noche anterior produjo un error, es responsabilidad del equipo para corregirlos tan pronto como sea posible.  
  
 Seguir un proceso de compilación diaria tiene muchas ventajas para el proyecto. En primer lugar, proporciona un latido regular (formado por la compilación diaria más las BVT automatizadas). En segundo lugar, utiliza BVT fuerza la integración con sistemas que es una tarea complicada, y hacerlo al principio de por sí reduce los riesgos del proyecto. Debido al tiempo necesario para completarlos, las pruebas de rendimiento y esfuerzo normalmente se realizan fuera del proceso de compilación diaria. Las pruebas de rendimiento y esfuerzo normalmente están programadas para realizarse en una compilación de hito en el proyecto.  
  
 Puede ser el proceso de compilación diaria y se ha utilizado, muy eficaz en soluciones de BizTalk. Sin embargo, deberá asegurarse de las tareas que se suelen dejar al final de los proyectos se realizan de forma iterativa desde el principio. Por ejemplo, la implementación de BizTalk Server es ciertamente no trivial. Es importante desarrollar scripts de implementación automatizada por adelantado. Si no lo hace, tendrá una implementación manual y sin implementar la solución muchas veces durante el proyecto, lo que costará más tiempo al final. Hay herramientas disponibles para controlar el proceso de compilación diaria; Visual Studio Team System y Team Foundation Server son la opción principal para muchas personas. Scripts de MSBuild pueden utilizarse para controlar los pasos del proceso de compilación. Otra alternativa es el código abierto [CruiseControl.NET herramienta](http://go.microsoft.com/fwlink/?LinkId=116093) (http://go.microsoft.com/fwlink/?LinkId=116093).  
  
> [!NOTE]  
>  Uso de esta herramienta no es compatible con Microsoft y Microsoft no ofrece ninguna garantía sobre la idoneidad de este programa. La utilización de este programa queda bajo su propia responsabilidad.  
  
 Para obtener más información acerca de cómo automatizar las pruebas mediante Microsoft Test manager, vea el tema [Running Automated Tests](http://go.microsoft.com/fwlink/?LinkID=208368) (http://go.microsoft.com/fwlink/?LinkID=208368) en la documentación en línea de Visual Studio 2010  
  
 Para obtener más información acerca de cómo automatizar el proceso de compilación con Visual Studio 2010, consulte [compilar la aplicación](http://go.microsoft.com/fwlink/?LinkID=208369) (HYPERLINK "<http://go.microsoft.com/fwlink/?LinkID=208369>" <http://go.microsoft.com/fwlink/?LinkID=208369>) en la documentación de Visual Studio 2010.  
  
## <a name="build-verification-testing"></a>Pruebas de comprobación de compilación  
 Las pruebas de comprobación de compilación normalmente consta de los siguientes elementos:  
  
- **Pruebas unitarias** -porque las pruebas unitarias suelen ser las primeras pruebas desarrollarse, lo ideal es que se debe crear antes de que realmente se ha escrito el código, si realmente utiliza un enfoque de desarrollo controlado por pruebas. Agregándolos en BVT durante las primeras fases de un proyecto, se proporciona al menos alguna cobertura de código inmediatamente. Como el número de pruebas funcionales y, por tanto, aumenta la cobertura de pruebas, puede optar por quitar las pruebas unitarias de la BVT.  
  
- **Pruebas de humo** -to-end pruebas funcionales que probar la funcionalidad básica de la solución. Si estos fallan, algo va mal en serio. Normalmente, estos poder ejecutarlo relativamente rápido.  
  
- **Pruebas funcionales** : estos escenarios de extremo a otro de destino también, pero en este caso todos los escenarios de prueba en el proyecto. Para proyectos grandes puede que tenga sentido para categorizar aún más las pruebas funcionales (por ejemplo, para habilitar un determinado componente va a probar de forma rápida, confiable y de forma aislada). Una vez haya firmado en su solución como funcionalmente correctas, se deben bloquear estas pruebas funcionales.  
  
- **Pruebas de comprobación de regresión** : cada vez que un error de la solución se encuentra y se ha corregido, comprobación de regresión se deben agregar casos de prueba para comprobar que se ha corregido el error y que no se reintroducen más adelante en el ciclo de vida del proyecto.  Estas pruebas suele ser casos que no se tratan en los casos de prueba funcionales. Debe esperar que las pruebas de comprobación de regresión aumentará en número incluso después de la solución ha quedado en vivo, si se detectan y se ha corregido errores nuevos.  
  
  En proyectos muy grandes, es posible que deba realizar a su BVT un subconjunto del conjunto de pruebas completa funcional (debido a la longitud de tiempo que tardan en ejecutarse). Para los proyectos más pequeños, pruebas BVT constituirá todo el conjunto. Obviamente, si va a integrar las BVT como parte de la compilación diaria, todo el proceso debe automatizarse. En el resto de este tema, nos centraremos en cómo puede usar BizUnit y otras herramientas para realizar esta acción.  
  
## <a name="functional-testing"></a>Pruebas funcionales  
 En el contexto de pruebas funcionales de las aplicaciones de BizTalk, probar un escenario de extremo a extremo específico. Al realizar este tipo de prueba, es útil para imagine BizTalk Server como una caja negra que probar funcionalmente desde una perspectiva externa. Por ejemplo, una prueba puede implicar la alimentación de un mensaje de entrada (con los valores conocidos) a un punto de conexión de la ubicación de recepción (para la ubicación del ejemplo, la dirección URL, FTP, lo que sea la elección del transporte). La prueba, a continuación, podría supervisar el número correcto de mensajes con los resultados correctos en el que se genera en el lado de envío. Esto puede parecer bastante sencilla. Sin embargo, cuando considere que algunos escenarios requieren entradas a entrar en un determinado orden y en un momento determinado, y esto compuesta con otros requisitos de la solución (como por ejemplo, cuando se graba los datos de seguimiento en BAM), queda claro que se pueden usadas para una herramienta y marco de trabajo orquestar esto.  
  
 Es fundamental que las pruebas de funcionamiento está diseñada para cubrir todas las rutas posibles a través de la solución. Esto debe incluir no sólo esos escenarios esperan en producción, pero también los trazados de error y las rutas de control de excepciones se han implementado, pero esperamos no tener que usar: está probando una frase utilizada normalmente para describir esto para "escenario mal día". Debe asegurarse de todas las orquestaciones, todos los tipos de mensaje permitidos y todas las ramas de código se aplican al conjunto de pruebas funcionales. Las secciones siguientes describen el desarrollo positivos y negativos casos de prueba funcionales para cubrir todas las rutas de código.  
  
 Para obtener más información acerca de las pruebas funcionales y las otras categorías de pruebas que se deben implementar antes de colocar una solución de BizTalk Server en el entorno de producción, vea el tema [lista de comprobación: probar la preparación operativa](http://go.microsoft.com/fwlink/?LinkId=160138) en el Guía de operaciones de BizTalk Server 2010 en [ http://go.microsoft.com/fwlink/?LinkId=160138 ](http://go.microsoft.com/fwlink/?LinkId=160138).  
  
### <a name="positive-tests"></a>Pruebas positivas  
  
-   Es importante al realizar las pruebas positivas para asegurarse de todas las combinaciones de mensajes, canalizaciones, orquestaciones y los puntos de conexión se pasan a través de la solución para que se aplican a todos los flujos de mensajes. Para asegurarse de que prueba todo el código de las rutas de acceso probablemente requerirá que procesar mensajes diferentes con contenido diferente.  
  
-   Al probar, use el tipo de transporte que se usará en producción. Desafortunadamente, con demasiada frecuencia, las pruebas funcionales se realizan solo con el adaptador de archivo cuando algún otro tipo de transporte que se usará en producción. Adoptar este enfoque es la configuración y el proyecto general fracaso más adelante.  
  
-   Validar la carga de todos los mensajes que se envían desde el sistema. Si los mensajes XML, debe validar su esquema y los campos de clave en el mensaje mediante expresiones XPath.  
  
-   Validar los datos de seguimiento almacenados en BAM (si se usa); cualquier otro dato que se deja en repositorios de datos externo debe tenerse en cuenta.  
  
-   Probar la ejecución de todas las reglas y directivas del motor de reglas de negocios (BRE) si la solución usa BRE.  
  
### <a name="negative-tests"></a>Pruebas negativas  
  
-   Asegúrese de que probar el control de mensajes no válidos a través del sistema. Debe comprobar que la estrategia elegida (rechazarlos antes de venir en BizTalk Server, o suspendan ellos) ha funcionado correctamente.  
  
-   Al probar el control de mensajes no válidos, asegúrese de que probar que se han implementado todas las orquestaciones de control de errores de recepción para controlar los mensajes suspendidos.  
  
-   Asegúrese de que los escenarios de error cubren todos los bloques de excepción en las orquestaciones.  No se puede probar esto adecuadamente es un problema común.  
  
-   Si utiliza transacciones de larga ejecución con el comportamiento de compensación, pruebe estos escenarios con mucho cuidado. Se trata de otra área donde pruebas inadecuadas incurrirá consecuencias graves en un entorno de producción.  
  
-   Asegúrese de que los errores se registran correctamente en los registros de error adecuado.  
  
## <a name="automation-is-key"></a>La automatización es clave  
 Para hacer todo esto de manera eficiente y eficaz, invierta el tiempo por adelantado para automatizar las pruebas. Las pruebas manuales son lentos, propenso a errores y costosa (en términos de tiempo y el costo). Cada vez que realiza un paso de prueba manual, agregue otro lote de tareas que deben controlarse mediante los recursos del proyecto (personas en el equipo). Al automatizar esto por adelantado, es posible obtener un valor devuelto de la inversión inicial que se necesita para desarrollar las pruebas cada vez que se ejecutan. Deben ejecutar de forma rápida y eficaz y ser repetible; buenas pruebas funcionales cada prueba también debe ser autónomo (debe ser independiente de cualquier otro; adoptar este enfoque le permite ejecutar varias pruebas secuencialmente como un conjunto de pruebas). Las pruebas funcionales siempre deben producir el mismo resultado. Pruebas funcionales mal escritas o código mal escrito producirá los resultados de pruebas diferentes entre ejecuciones de pruebas, dando lugar a confusión y pérdida de tiempo investigando la causa del error.  
  
 Es importante minimizar el esfuerzo de desarrollo necesario para escribir cada prueba funcional. Normalmente es más costosa resulta algo (en términos de tiempo de desarrollo), producen menos casos de prueba es probable que acabe. Esto significa que tendrá un nivel inferior de la cobertura de pruebas a través de su código. Mediante el uso de un marco de pruebas, puede desarrollar casos de prueba más rápidos y sencillo y, por lo tanto, que sea más fácil obtener cobertura de código completo. La mayoría de los marcos de pruebas buena utilizan un enfoque declarativo para definir las pruebas. (Es decir, la configuración de una prueba se almacena en un archivo de configuración, que normalmente es un archivo XML). Uso de una buena prueba framework permite desarrollar una completa funcional conjunto de pruebas de una manera ágil y confiable y evita tener que "reinventar la rueda" una y otra vez, por así decirlo.  
  
## <a name="msbuild-support-for-biztalk-server-projects"></a>Compatibilidad para MSBUILD para proyectos de BizTalk Server  
 BizTalk Server proporciona compatibilidad para la plataforma de motor de compilación de Microsoft (MSBUILD), lo que permite la creación de proyectos administrados en los entornos de laboratorio de compilación donde no está instalado Visual Studio. Compilar proyectos de una línea de comandos y la funcionalidad avanzada que incluye MSBUILD, registro y el procesamiento por lotes se adapta a MSBUILD. Para obtener más información acerca de MSBUILD, vea [información general sobre MSBuild](http://go.microsoft.com/fwlink/?LinkId=131739) (http://go.microsoft.com/fwlink/?LinkId=131739).  
  
## <a name="see-also"></a>Vea también  
 [Implementación de pruebas automatizadas](../technical-guides/implementing-automated-testing.md)