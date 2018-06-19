---
title: Análisis de modelo de amenazas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TMA, about TMA
- TMA
- TMA, procedure steps
ms.assetid: dfbf46aa-0a35-4925-8718-df8591efc279
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06f5de73434d2c3a7bf67e659c6566b530b38aeb
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
ms.locfileid: "22279916"
---
# <a name="threat-model-analysis"></a>Análisis de modelo de amenazas
El análisis de modelo de amenazas (TMA) es un análisis que ayuda a determinar los riesgos de seguridad que pueden acaecer en un producto, aplicación, red o entorno, así como la forma en la que se aparecen los ataques. El objetivo consiste en determinar cuáles son las amenazas que requieren mitigación y los modos de hacerlo.  
  
 Esta sección proporciona información de alto nivel acerca del proceso TMA. Para obtener más información, consulte el capítulo 4 de *Writing Secure Code, segunda edición*, de Michael Howard y David LeBlanc.  
  
 Algunas de las ventajas de un TMA son:  
  
-   Facilita la comprensión de la aplicación.  
  
-   Ayuda a detectar errores  
  
-   Puede ayudar a los miembros del nuevo equipo a entender la aplicación con mayor profundidad.  
  
-   Contiene información importante para otros equipos que trabajan en su aplicación.  
  
-   Resulta de utilidad para los evaluadores.  
  
 Los pasos de nivel alto para llevar a cabo un TMA son los siguientes:  
  
-   Paso 1. Recopilar información básica  
  
-   Paso 2. Crear y analizar el modelo de amenazas  
  
-   Paso 3. Analizar las amenazas  
  
-   Paso 4. Identificar las tecnologías y técnicas de mitigación  
  
-   Paso 5. Modelo de seguridad de documento y las consideraciones de implementación  
  
-   Paso 6. Implementar y probar las mitigaciones  
  
-   Paso 7. Mantener el modelo de amenazas sincronizado con el diseño  
  
## <a name="step-1-collect-background-information"></a>Paso 1. Recopilar información básica  
 Para preparar un TMA correcto, debe recopilar información básica. Resulta de utilidad analizar el entorno de destino (una aplicación, un programa o la infraestructura completa) de la manera siguiente:  
  
-   Identificar escenarios de casos de uso. En cada escenario de caso de uso de su entorno de destino, identifique cómo espera que su empresa utilice el entorno de destino, así como las limitaciones y restricciones del entorno de destino. Esta información ayuda a definir el ámbito de discusión del modelo de amenazas, y proporciona los indicadores a los activos (cualquier elemento de valor de la empresa, como, por ejemplo, la información y los equipos) y los puntos de entrada.  
  
-   Crear un diagrama de flujo de datos (DFD) para cada escenario. Asegúrese de que profundiza lo suficiente para entender las amenazas.  
  
-   Determinar los límites y el ámbito del entorno de destino.  
  
-   Comprender los límites entre los componentes que son de confianza y los que no lo son.  
  
-   Comprender el modelo de administración y configuración de cada componente.  
  
-   Crear una lista de dependencias externas.  
  
-   Crear una lista de supuestos acerca de los componentes de los que depende cada componente. Esto ayuda a validar los elementos de seguimiento, los elementos de acción y los supuestos derivados de varios componentes con otros equipos.  
  
## <a name="step-2-create-and-analyze-the-threat-model"></a>Paso 2. Crear y analizar el modelo de amenazas  
 Después de recopilar la información básica, debe concertar una o varias reuniones sobre el modelo de amenazas. Asegúrese de que a dicha reunión asiste, al menos, un miembro de cada disciplina de desarrollo, como, por ejemplo, los administradores de programa, programadores y evaluadores. Procure también recordar a los asistentes que el objetivo de la reunión se encuentra en detectar amenazas, no en solucionarlas. Durante la reunión sobre el modelo de amenazas, lleve a cabo las siguientes acciones:  
  
-   Examine el DFD en cada caso de uso. En cada uno de estos casos, identifique los elementos siguientes:  
  
    -   Puntos de entrada  
  
    -   Límites de confianza  
  
    -   Flujo de datos desde el punto de entrada hasta su última ubicación (y al contrario)  
  
-   Anote los activos implicados.  
  
-   Aborde cada DFD y busque las amenazas en las siguientes categorías para todas las entradas de DFD: **S**poofing identificar, **T**lteración con datos, **R**epudiation, **I**revelación de información, **d.** denegación de servicio, y **E**levación de privilegios.  
  
-   Cree una lista de amenazas identificadas. Se recomienda que esta lista incluya lo siguiente: título, descripción breve (incluyendo los árboles de amenazas), activo (activo), impactos, riesgo, técnicas de mitigación, estado de mitigación y número de error.  
  
    > [!NOTE]
    >  Puede agregar las categorías de riesgo, técnicas de mitigación y estado de mitigación al revisar las amenazas. No invierta demasiado tiempo en estas áreas durante la reunión sobre el modelo de amenazas.  
  
## <a name="step-3-review-threats"></a>Paso 3. Analizar las amenazas  
 Una vez identificadas las amenazas del entorno, debe valorar el riesgo de cada una de ellas y determinar cómo va a actuar ante ellas. Para ello puede convocar nuevas reuniones o utilizar el correo electrónico. Puede usar las siguientes categorías de efecto para calcular la exposición al riesgo: **d.** años potenciales, **R**apacidad de reproducción, **E**provechamiento, **A**usuarios afectados y **d.** capacidad de descubrimiento.  
  
 Cuando disponga de una lista de las amenazas que ponen en peligro su entorno de destino en función del riesgo, debe determinar cómo actuará ante cada una. Su respuesta puede ser no hacer nada (aunque ésta no suele ser una buena opción), advertir a los usuarios del posible problema o eliminar el problema o solucionarlo.  
  
## <a name="step-4-identify-mitigation-techniques-and-technologies"></a>Paso 4. Identificar las tecnologías y técnicas de mitigación  
 Después de identificar las amenazas que se van a solucionar, debe determinar las técnicas de mitigación disponibles para cada amenaza, así como la tecnología más adecuada para reducir su efecto.  
  
 Por ejemplo, en función de los detalles del entorno de destino, es posible reducir el efecto de las amenazas de alteración de datos con técnicas de autorización. A continuación, debe determinar la tecnología de autorización más adecuada, como, por ejemplo, las listas de control de acceso discrecional (DACL), los permisos o las restricciones IP.  
  
> [!IMPORTANT]
>  Al evaluar las tecnologías y técnicas de mitigación que se van a utilizar, debe tener en cuenta los fundamentos de la empresa y aquellas directivas propias que pueden afectar la elección de técnicas de mitigación determinadas.  
  
 Una vez que ha completado el TMA, realice las siguientes opciones:  
  
-   Documentar el modelo de seguridad y las consideraciones de implementación  
  
-   Implementar y probar las mitigaciones  
  
-   Mantener el modelo de amenazas sincronizado con el diseño  
  
## <a name="step-5-document-security-model-and-deployment-considerations"></a>Paso 5. Modelo de seguridad de documento y las consideraciones de implementación  
 Resulta de gran valor documentar todo aquello que se descubre durante el TMA y la forma en que se decide reducir el efecto de las amenazas de su entorno de destino. Esta documentación puede ser de gran ayuda en los controles de calidad (QA), pruebas y soportes, así como para el personal de operaciones. Incluya información sobre las aplicaciones que interactúan o funcionan con el entorno de destino, así como los requisitos y recomendaciones de topologías y servidores de seguridad.  
  
## <a name="step-6-implement-and-test-mitigations"></a>Paso 6. Implementar y probar las mitigaciones  
 Cuando el equipo está preparado para solucionar las amenazas que se han identificado durante el TMA, asegúrese de que utiliza listas de comprobación de implementación y desarrollo. Gracias a ellas podrá seguir las normativas de implementación y código seguro que le ayudarán a minimizar la entrada de nuevas amenazas.  
  
 Tras implementar una mitigación, pruébela para asegurarse de que proporciona el nivel de protección adecuado para la amenaza.  
  
## <a name="step-7-keep-the-threat-model-in-sync-with-design"></a>Paso 7. Mantener el modelo de amenazas sincronizado con el diseño  
 A medida que agrega aplicaciones nuevas, servidores y otros elementos a su entorno, asegúrese de que revisa los hallazgos del análisis de modelo de amenazas y de que realiza otros análisis para obtener nuevas funciones.  
  
## <a name="see-also"></a>Vea también  
[Casos prácticos de seguridad para pequeñas y medianas empresas](../core/security-case-studies-for-small-to-medium-sized-companies.md)   
 [Escenarios de ejemplo para el análisis de modelo de amenaza](../core/sample-scenarios-for-threat-model-analysis.md)