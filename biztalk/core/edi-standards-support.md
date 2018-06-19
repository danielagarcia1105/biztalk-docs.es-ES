---
title: Compatibilidad con los estándares EDI | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2ef14c5-5f12-40e2-93d7-59b5c5a0d641
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebb7ab3abb9a4bc547d920614e1a1839a85c593b
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007925"
---
# <a name="edi-standards-support"></a>Compatibilidad de estándares EDI
BizTalk Server proporciona para la compatibilidad de diseño y tiempo de ejecución con cuatro estándares de codificación. En la tabla siguiente se enumeran los estándares de codificación con vínculos a información complementaria.  
  
|Estándar de codificación|Sector industrial|Referencias|  
|-----------------------|----------------------|----------------|  
|UN/EDIFACT|Industria en general|[Sitio Web de estándares](http://go.microsoft.com/fwlink/?LinkId=77532) (referencia a la carga)<br /><br /> [Regla de codificación](http://go.microsoft.com/fwlink/?LinkId=77534) por ISO 9735-4.1|  
|X12|Industria en general|[Sitio Web de estándares](http://go.microsoft.com/fwlink/?LinkID=28673)<br /><br /> [Desarrollo de especificaciones](http://go.microsoft.com/fwlink/?LinkId=77535)|  
|EANCOM|Comercial|[Sitio Web de estándares](http://go.microsoft.com/fwlink/?LinkId=92861)|  
|HIPAA X12N|Asistencia sanitaria|[Guía de implementación de HIPAA](http://go.microsoft.com/fwlink/?LinkId=77541)<br /><br /> [Especificaciones de HIPAA](http://go.microsoft.com/fwlink/?LinkId=77542)|  
  
> [!NOTE]
>  Los esquemas de EANCOM son un subconjunto de EDIFACT. EANCOM sigue las mismas reglas de codificación que EDIFACT.  
  
> [!NOTE]
>  KEDIFACT es un estándar distinto, pero se basa en gran medida en el estándar EDIFACT.  
  
## <a name="x12-and-edifact"></a>X12 y EDIFACT  
 Dos estándares, ANSI X12 y UN/EDIFACT, intervienen en más del 90% de todos los mensajes EDI intercambiados en todo el mundo:  
  
-   El estándar de mensajes internacional UN/EDIFACT EDI (EDI para administración, comercio y negocios) ha sido desarrollado por la Comisión Económica para Europa de las Naciones Unidas (UN/ECE), que continúa con su mantenimiento. También se le conoce sólo como EDIFACT.  
  
-   El estándar para mensajes estadounidense, X12 EDI, ha sido desarrollado por el Accredited Standards Committee (ASC) X12, que continúa con su mantenimiento y que cuenta con la aprobación del American National Standards Institute (ANSI).  
  
 EDIFACT se basa en gran medida en los Estados Unidos X12 estándares. Los dos estándares EDI son muy parecidos en cuanto a su estructura. Las diferencias estriban en lo siguiente:  
  
-   Los elementos estructurales reciben nombres muy distintos en ambos estándares. Por ejemplo, el encabezado de control de intercambio es un elemento de datos ISA en X12 y un elemento de datos UNB en EDIFACT.  
  
-   Aunque existen muchas asignaciones de conjuntos de transacciones entre ambos estándares, los conjuntos de transacciones reciben nombres muy distintos en ambos. Por ejemplo, un pedido es un conjunto de transacciones 850 en X12, mientras que es un conjunto de transacciones ORDERS en EDIFACT.  
  
-   EDIFACT cuenta con un segmento de encabezado opcional UNA para establecer elementos estructurales como separadores o delimitadores y la notación decimal, invalidando los valores predeterminados definidos en una canalización.  
  
-   X12 tiene dos confirmaciones (una confirmación técnica, denominada TA1, y una confirmación funcional denominada 997), mientras que EDIFACT cuenta con una confirmación completa denominada CONTRL.  
  
-   X12 recomienda la codificación ASCII, mientras que EDIFACT recomienda la codificación UTF8.  
  
 BizTalk Server es compatible con el estándar KEDIFACT (EDIFACT coreano). KEDIFACT sigue la guía de implementación de mensajes de UN/EDIFACT, por lo que se basa en gran medida en EDIFACT. Sin embargo, existen diferencias entre KEDIFACT y X12 y EDIFACT. KEDIFACT usa diversos esquemas EDI específicos de KEDIFACT y usa la página de códigos KECA.  
  
## <a name="hipaa"></a>HIPAA  
 BizTalk Server admite X12 de procesamiento y, puesto que el procesamiento de HIPAA es un derivado de X12 de procesamiento, BizTalk Server admite el procesamiento de HIPAA. Cuando se vean referencias a X12 admite en este documento, también se aplica al procesamiento de HIPAA.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona compatibilidad adicional específica de HIPAA:  
  
-   Un grupo de esquemas de documentos HIPAA de la versión 4010A1. Para obtener más información sobre los esquemas de documento EDI e HIPAA en BizTalk Server, vea [esquemas de documento EDI](../core/edi-document-schemas.md).  
  
-   Un conjunto de esquemas de documentos HIPAA de la versión 5010. Para obtener más información, consulte [HIPAA 5010 de versión de esquema de documento](../core/hipaa-document-schema-version-5010.md).  
  
-   División de subdocumentos HIPAA. Para obtener más información, consulte [dividir subdocumentos HIPAA](../core/splitting-hipaa-subdocuments.md).  
  
-   Compatibilidad con los dos primeros niveles de pruebas WEDI SNIP: X12 integridad de la sintaxis y los requisitos de la [Guía de implementación de HIPAA](http://go.microsoft.com/fwlink/?LinkId=77541).  
  
 BizTalk Server proporciona compatibilidad con HIPAA como parte de la funcionalidad nativa de EDI de BizTalk Server. Para obtener más información, consulte [compatibilidad de EDI en BizTalk Server](../core/edi-support-in-biztalk-server2.md).  
  
## <a name="eancom"></a>EANCOM  
 BizTalk Server admite el procesamiento de EDIFACT y, puesto que el procesamiento de EANCOM se deriva del procesamiento de EDIFACT, BizTalk Server admite el procesamiento de EANCOM. Cuando se vean referencias a la compatibilidad con EDIFACT en este documento, también son aplicables al procesamiento de EANCOM.  
  
 BizTalk Server proporciona compatibilidad adicional específica de EANCOM:  
  
-   Un grupo de esquemas de documentos EANCOM de las versiones EAN94, EAN97 Y EAN02. Para obtener más información sobre los esquemas de documento EDI y EANCOM en BizTalk Server, vea [esquemas de documento EDI](../core/edi-document-schemas.md).  
  
## <a name="see-also"></a>Vea también  
 [Estructura de mensaje EDI](../core/edi-message-structure.md)   
 [Esquemas de documentos EDI](../core/edi-document-schemas.md)