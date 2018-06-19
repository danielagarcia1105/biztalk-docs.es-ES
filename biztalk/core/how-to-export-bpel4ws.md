---
title: Cómo exportar BPEL4WS | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BPEL4WS, exporting
- BPEL4WS, restrictions
- orchestrations, BPEL4WS
ms.assetid: 4648dfcf-cf48-4471-b088-07252c080fb8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b16c2e34b498a9fb8d5fd3f6e69f022c2876a763
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253836"
---
# <a name="how-to-export-bpel4ws"></a>Cómo exportar BPEL4WS
Puede exportar una orquestación de BizTalk existente al lenguaje BPEL4WS.  
  
> [!IMPORTANT]
>  Esta versión de BizTalk Server es compatible con BPEL4WS 1.1. No es compatible con BPEL4WS 1.0 para realizar importaciones o exportaciones.  
  
 Si está exportando, la compatibilidad con BPEL4WS para la compilación requiere que las orquestaciones solo contengan características comunes entre XLANG/s y BPEL4WS, o características que se puedan traducir a BPEL4WS sin que se vea afectado el comportamiento.  
  
## <a name="export-restrictions-on-orchestrations-for-bpel4ws-compliance"></a>Restricciones de exportación en las orquestaciones para la compatibilidad con BPEL4WS  
  
-   No puede usar la forma Orquestación de llamada ni la forma Iniciar orquestación.  
  
-   No puede utilizar la forma Transformación.  
  
-   No puede invocar métodos en componentes .NET personalizados.  
  
-   No puede aplicar un tiempo de espera a una transacción de larga ejecución.  
  
-   La orquestación no acepta parámetros.  
  
-   Los controladores de compensación que se pueden llamar no pueden tener parámetros.  
  
-   Los tipos de variables deben ser compatibles en XPATH.  
  
-   No puede usar la forma Suspender.  
  
-   Los valores literales deben ser de uno de los siguientes tipos:  
  
     boolean, char, byte, sbyte, int32, uint32, int64, uint64, single, double o string  
  
-   Solo se permiten operadores aritméticos en operandos de los siguientes tipos numéricos:  
  
     byte, sbyte, int32, uint32, int64, uint64, single o double  
  
-   No se pueden aplicar operadores relacionales al tipo char.  
  
-   No puede hacer referencia a una propiedad servicelink en una expresión.  
  
-   No se puede realizar ninguna acción entre una **enviar** forma y un **recepción** forma que utilicen el mismo puerto de solicitud-respuesta de salida.  
  
-   No puede hacer referencia de forma indirecta a un servicio Web; por ejemplo, a través de una referencia a otro proyecto que contenga una referencia. Debe hacer referencia de forma explícita al servicio Web en el proyecto.  
  
-   No puede especificar un valor DateTime o TimeSpan constante en un retraso. En su lugar, use una de las clases de conversión en el espacio de nombres System.Xml:  
  
     Para un valor DateTime constante: System.Xml.XmlConvert.ToDateTime, por ejemplo System.Xml.XmlConvert.ToDateTime("2004-04-15")  
  
     Para un valor TimeSpan constante: System.Xml.XmlConvert.ToTimeSpan, por ejemplo System.Xml.XmlConvert.ToTimeSpan("2004-04-15")  
  
> [!NOTE]
>  Los literales de carácter se exportan como enteros sin signo. Por ejemplo, "a" se exporta como 97, "b" se exporta como 98, etc.  
  
> [!CAUTION]
>  Los nombres de identificador deben ajustarse a la especificación del Lenguaje de marcado extensible (XML) 1.0 de W3C.  
  
#### <a name="to-export-an-orchestration-to-bpel4ws"></a>Para exportar una orquestación al lenguaje BPEL4WS  
  
1.  Agregue un nuevo elemento de tipo Orquestación de BizTalk al proyecto.  
  
2.  Haga clic en la superficie de diseño para abrir la ventana Propiedades de orquestación.  
  
3.  Establecer **Exportable a módulo** en True.  
  
4.  Tipo en el espacio de nombres que desee para **módulo XML Target Namespace**.  
  
5.  Establecer **Exportable a orquestación** en True.  
  
6.  Tipo en el espacio de nombres que desee para **orquestación XML Target Namespace**.  
  
7.  En el Explorador de soluciones, haga clic en el. Archivo ODX para la orquestación.  
  
8.  Seleccione **exportar a BPEL**.  
  
     La orquestación se exportará a BPEL4WS. Consulte las ventanas Resultados y Lista de tareas para confirmar que la orquestación se ha exportado correctamente o diagnosticar problemas. Una vez finalizada correctamente la exportación, se creará un archivo .WSDL y un archivo .BPEL en el directorio del proyecto.  
  
> [!NOTE]
>  Si la orquestación contiene una asignación a un vínculo de rol (vínculo de servicio) o una asignación literal a un puerto dinámico, BizTalk genera una referencia ficticia de extremo BPEL4WS y una advertencia.  
  
## <a name="see-also"></a>Vea también  
 [Cómo importar BPEL4WS](../core/how-to-import-bpel4ws.md)   
 [XLANG-s para las conversiones de tipo de BPEL4WS](../core/xlang-s-to-bpel4ws-type-conversions.md)