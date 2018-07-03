---
title: Compatibilidad con estándares EDI | Microsoft Docs
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
ms.openlocfilehash: ebb4d85b4972991054914baea2014b6d268a24eb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007133"
---
# <a name="edi-standards-support"></a>Compatibilidad de estándares EDI
BizTalk Server proporciona compatibilidad de diseño y tiempo de ejecución con cuatro estándares de codificación. En la tabla siguiente se enumeran los estándares de codificación con vínculos a información complementaria.  
  
|Estándar de codificación|Sector industrial|References|  
|-----------------------|----------------------|----------------|  
|UN/EDIFACT|Industria en general|[Sitio Web de estándares](http://go.microsoft.com/fwlink/?LinkId=77532) (referencia de carga)<br /><br /> [Regla de codificación](http://go.microsoft.com/fwlink/?LinkId=77534) por ISO 9735-4.1|  
|X12|Industria en general|[Sitio Web de estándares](http://go.microsoft.com/fwlink/?LinkID=28673)<br /><br /> [Desarrollo de especificaciones](http://go.microsoft.com/fwlink/?LinkId=77535)|  
|EANCOM|Venta directa|[Sitio Web de estándares](http://go.microsoft.com/fwlink/?LinkId=92861)|  
|HIPAA X12N|Asistencia sanitaria|[Guía de implementación de HIPAA](http://go.microsoft.com/fwlink/?LinkId=77541)<br /><br /> [Especificaciones de HIPAA](http://go.microsoft.com/fwlink/?LinkId=77542)|  
  
> [!NOTE]
>  Los esquemas de EANCOM son un subconjunto de EDIFACT. EANCOM sigue las mismas reglas de codificación que EDIFACT.  
  
> [!NOTE]
>  KEDIFACT es un estándar distinto, pero se basa en gran medida en el estándar EDIFACT.  
  
## <a name="x12-and-edifact"></a>X12 y EDIFACT  
 Dos estándares, ANSI X12 y UN/EDIFACT, intervienen en más del 90% de todos los mensajes EDI intercambiados en todo el mundo:  
  
- El estándar de mensajes internacional UN/EDIFACT EDI (EDI para administración, comercio y negocios) ha sido desarrollado por la Comisión Económica para Europa de las Naciones Unidas (UN/ECE), que continúa con su mantenimiento. También se le conoce sólo como EDIFACT.  
  
- El estándar para mensajes estadounidense, X12 EDI, ha sido desarrollado por el Accredited Standards Committee (ASC) X12, que continúa con su mantenimiento y que cuenta con la aprobación del American National Standards Institute (ANSI).  
  
  EDIFACT se basa en gran medida de Estados Unidos. X12 estándares. Los dos estándares EDI son muy parecidos en cuanto a su estructura. Las diferencias estriban en lo siguiente:  
  
- Los elementos estructurales reciben nombres muy distintos en ambos estándares. Por ejemplo, el encabezado de control de intercambio es un elemento de datos ISA en X12 y un elemento de datos UNB en EDIFACT.  
  
- Aunque existen muchas asignaciones de conjuntos de transacciones entre ambos estándares, los conjuntos de transacciones reciben nombres muy distintos en ambos. Por ejemplo, un pedido es un conjunto de transacciones 850 en X12, mientras que es un conjunto de transacciones ORDERS en EDIFACT.  
  
- EDIFACT cuenta con un segmento de encabezado opcional UNA para establecer elementos estructurales como separadores o delimitadores y la notación decimal, invalidando los valores predeterminados definidos en una canalización.  
  
- X12 tiene dos confirmaciones (una confirmación técnica, denominada TA1, y una confirmación funcional denominada 997), mientras que EDIFACT cuenta con una confirmación completa denominada CONTRL.  
  
- X12 recomienda la codificación ASCII, mientras que EDIFACT recomienda la codificación UTF8.  
  
  BizTalk Server admite el estándar KEDIFACT (EDIFACT coreano). KEDIFACT sigue la guía de implementación de mensajes de UN/EDIFACT, por lo que se basa en gran medida en EDIFACT. Sin embargo, existen diferencias entre KEDIFACT y X12 y EDIFACT. KEDIFACT usa diversos esquemas EDI específicos de KEDIFACT y usa la página de códigos KECA.  
  
## <a name="hipaa"></a>HIPAA  
 BizTalk Server admite procesamiento de X12 y, puesto que el procesamiento de HIPAA deriva del procesamiento de X12, BizTalk Server admite procesamiento de HIPAA. Cuando se vean referencias a X12 admitir en este documento, también se aplica al procesamiento de HIPAA.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona compatibilidad adicional específica de HIPAA:  
  
- Un grupo de esquemas de documentos HIPAA de la versión 4010A1. Para obtener más información sobre los esquemas de documentos EDI e HIPAA en BizTalk Server, consulte [esquemas de documentos EDI](../core/edi-document-schemas.md).  
  
- Un conjunto de esquemas de documentos HIPAA de la versión 5010. Para obtener más información, consulte [HIPAA 5010 de versión de esquema de documento](../core/hipaa-document-schema-version-5010.md).  
  
- División de subdocumentos HIPAA. Para obtener más información, consulte [división de subdocumentos HIPAA](../core/splitting-hipaa-subdocuments.md).  
  
- Compatibilidad con los dos primeros niveles de pruebas WEDI SNIP: X12 integridad de la sintaxis y los requisitos de la [Guía de implementación de HIPAA](http://go.microsoft.com/fwlink/?LinkId=77541).  
  
  BizTalk Server proporciona compatibilidad con HIPAA como parte de la funcionalidad nativa de EDI de BizTalk Server. Para obtener más información, consulte [compatibilidad con EDI en BizTalk Server](../core/edi-support-in-biztalk-server2.md).  
  
## <a name="eancom"></a>EANCOM  
 BizTalk Server admite procesamiento de EDIFACT y, puesto que el procesamiento de EANCOM es un derivado de procesamiento de EDIFACT, BizTalk Server admite procesamiento de EANCOM. Cuando se vean referencias a la compatibilidad con EDIFACT en este documento, también son aplicables al procesamiento de EANCOM.  
  
 BizTalk Server proporciona compatibilidad adicional específica de EANCOM:  
  
-   Un grupo de esquemas de documentos EANCOM de las versiones EAN94, EAN97 Y EAN02. Para obtener más información sobre los esquemas de documentos EDI y EANCOM en BizTalk Server, consulte [esquemas de documentos EDI](../core/edi-document-schemas.md).  
  
## <a name="see-also"></a>Vea también  
 [Estructura de los mensajes EDI](../core/edi-message-structure.md)   
 [Esquemas de documentos EDI](../core/edi-document-schemas.md)