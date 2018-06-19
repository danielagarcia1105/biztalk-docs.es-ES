---
title: Compatibilidad con EDI | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d4f50a9-fc55-400c-a63c-40b697425fea
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04cd9c14b9c3663bdf332155cc9824e1681ca7a6
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710299"
---
# <a name="edi-support-in-biztalk-server"></a>Compatibilidad con EDI en BizTalk Server
EDI está integrada en BizTalk Server y es un componente opcional al instalar y configurar BizTalk Server. 
  
## <a name="feature-set-comparison-chart"></a>Comparación de conjunto de características  
 La siguiente tabla muestra la compatibilidad EDI que se incluyen con BizTalk Server.
  
|Característica|Comentario|  
|---|---|
|Modificación del segmento ISA en el conjunto de transacciones| Crear acuerdos específicos de conjuntos de transacciones|  
|ISA11: Estados Unidos u otros estándares| |  
|ISA12: Versión de Control de intercambio| |  
|ISA13: Número de Control de intercambio (aumento del número)| |  
|ISA15: Prueba o producción| |  
|Modificación del segmento GS en el nivel de documento o transacción| |  
|GS remitente/receptor de GS permitido sea distinto a ISA| |  
|Identificadores de documento de entrada distinto de ISA y GS de salida| |  
|GS01: Capacidad para cambiar el tipo de documento| |  
|GS04: Fecha (posibilidad de cambiar el formato)|Contiene la interfaz de usuario para seleccionar formatos como SSAAMMDD y AAMMDD|  
|GS05: Hora (posibilidad de cambiar el formato)|Contiene la interfaz de usuario para seleccionar formatos como HHMM, HHMMSS y HHMMSSdd|  
|GS06: Cambiar el número de control| |  
|GS07: Agencia código| |  
|GS08: Posibilidad de colocarlo en versiones estándar| |  
|Capacidad de reemplazar el sobre EDI en tiempo de ejecución| |  
|Esquemas EDI personalizados| |  
|Organización/configuración de entidades|Crear entidad independiente y contratos. Crear acuerdos a partir de plantillas.|  
|Enrutamiento a través de la definición de documento de documentos EDI| |  
|Confirmaciones 997 automáticas a socios comerciales|Configuración específica para perfiles de negocio|  
|Confiable de mensajería a través de 997 de salida EDI| |  
|Compatibilidad con EDIFACT|Admite D93 a D05 según ISO 9735 v4.1|  
|Admitir X12|2040 a 5030|  
|Compatibilidad con HIPAA| Acelerador de Microsoft BizTalk para HIPAA (BTAHIPAA) como parte de la funcionalidad nativa de EDI|  
|Posibilidad de quitar enumeradores/listas de códigos|Utilice el Editor de Visual Studio/BizTalk|  
|AS2 Envío y recepción| AS2 es el certificado Drummond para la compatibilidad con varios archivos adjuntos, la compatibilidad con la conservación de nombres de archivo y la interoperabilidad.|  
|Conservación de nombre de archivo de AS2| |  
|Mensajería confiable de AS2| |  
|Procesamiento por lotes (acumulación de varios tipos de transacciones en una única transacción)|Admite varias configuraciones de lote para cada perfil de negocio|  
|Entrada de procesamiento por lotes: intercambio XML (conservar un intercambio "por lotes" entrante) o el XML de conjunto de transacciones basado en las opciones de configuración|También admite la entrada-anulando, es decir, división de intercambios en Xml de conjunto de transacciones individual|  
|Intercambio y conjunto de transacciones generación y validación en tiempo de diseño en Visual Studio| |  
|Conciliación y generación de TA1 (confirmación técnica)| |  
|Marcas de validación XSD y EDI opcional| |  
|Formato de documento/definición en nivel GS| |  
  
## <a name="see-also"></a>Vea también  
 [Compatibilidad con los estándares EDI](../core/edi-standards-support.md)   
 [Compatibilidad con esquema de documento EDI](../core/edi-document-schema-support.md)   
 [Compatibilidad de juegos de caracteres de EDI](../core/edi-character-set-support.md)