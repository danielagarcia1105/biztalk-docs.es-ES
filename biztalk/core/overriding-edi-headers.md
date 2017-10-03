---
title: Reemplazar los encabezados EDI | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 16c19d3d-eab2-4d44-8752-25aeadb537a4
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 510a3817d0fd99d43b6da9462c74dd8bc7c1bdf0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="overriding-edi-headers"></a>Invalidar los encabezados de EDI
Al enviar un intercambio con codificación EDI, el sobre EDI aplicado al mensaje está basado normalmente en las propiedades de EDI del acuerdo receptor o en las propiedades del acuerdo de reserva. No obstante, a menudo resulta útil establecer las propiedades del sobre EDI basándose en los valores generados en tiempo de ejecución.  
  
 En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], puede utilizar las propiedades del contexto EdiOverride para especificar los valores utilizados para generar el sobre EDI en los documentos de salida.  
  
## <a name="using-edioverride-context-properties"></a>Utilizar las propiedades del contexto EdiOverride  
 Las propiedades del contexto EdiOverride proporcionan una manera de invalidar todos o parte de los valores utilizados para generar el sobre EDI. La canalización de envío EDI utilizará la propiedad del contexto EdiOverride que contiene un valor válido para construir el sobre. Si no se rellena una propiedad, la canalización utilizará el valor especificado en las propiedades del acuerdo o en las propiedades del acuerdo de reserva, si no se ha definido un acuerdo. Si una propiedad contiene un valor no válido, la canalización suspenderá el mensaje y notificará un error de validación.  
  
> [!NOTE]
>  Solo se utilizan los valores especificados en la colección EdiOverride si la propiedad `EdiOverride.OverrideEdiHeader` se escribe en el contexto de un mensaje y contiene el valor "True".  
>   
>  El valor predeterminado no está establecido.  
  
### <a name="edioverride-properties-for-x12-envelope-values"></a>Propiedades EdiOverride para valores de sobre X12  
 En la siguiente tabla se muestran las propiedades del contexto EdiOverride y el encabezado de sobre X12 correspondiente:  
  
|Encabezado|Propiedades|  
|------------|----------------|  
|Encabezado de control de intercambio (ISA)|ISA01, ISA02, ISA03, ISA04, ISA05, ISA06, ISA07, ISA08, ISA09, ISA10, ISA11, ISA12, ISA13, ISA14, ISA15, ISA16|  
|Encabezados de grupo funcional (GS)|GS01, GS02, GS03, GS04, GS05, GS06, GS07, GS08|  
|Encabezado del conjunto de transacciones|ST02|  
  
### <a name="edioverride-properties-for-edifact-envelope-values"></a>Propiedades EdiOverride para valores de sobre EDIFACT  
 En la siguiente tabla se muestran las propiedades del contexto EdiOverride y el segmento de sobre EDIFACT correspondiente:  
  
|Segment|Propiedades|  
|-------------|----------------|  
|Notificación del servicio (UNA)|UNA1, UNA2, UNA3, UNA4, UNA5, UNA6, UNA6Suffix|  
|Encabezado de control de intercambio (UNB)|UNB1_1, UNB1_2, UNB2_1, UNB2_2, UNB2_3, UNB3_1, UNB3_2, UNB3_3, UNB4_1, UNB4_2, UNB5, UNB6_1, UNB7, UNB8, UNB9, UNB10, UNB11|  
|Encabezados de grupo funcional (UNG)|UNG1, UNG2_1, UNG2_2, UNG3_1, UNG3_2, UNG4_1, UNG4_2, UNG5, UNG6, UNG7_1, UNG7_2, UNG7_3, UNG8|  
|Encabezado de mensaje (UNH)|UNH1|  
  
 Puesto que los segmentos UNA y UNG de EDIFACT son opcionales, las propiedades GenerateUNA y GenerateUNG pueden usarse para determinar si estos encabezados se generado, independientemente de la **aplicar segmento UNA** configuración del acuerdo. En las siguientes tablas se muestran los valores que producen la generación de estos segmentos:  
  
|Propiedad del contexto GenerateUNA|Configuración del acuerdo Aplicar segmento UNA|Comportamiento del motor|  
|----------------------------------|-----------------------------------------|---------------------|  
|TRUE|ACTIVADA|Generar UNA|  
|TRUE|DESACTIVADA|Generar UNA|  
|FALSE|ACTIVADA|No generar UNA|  
|FALSE|DESACTIVADA|No generar UNA|  
|No está presente (OverrideEDIHeader es false)|ACTIVADA|Generar UNA|  
|No está presente (OverrideEDIHeader es false)|DESACTIVADA|No generar UNA|  
  
|Propiedad del contexto GenerateUNG|Configuración del acuerdo Aplicar segmentos UNG|Comportamiento del motor|  
|----------------------------------|------------------------------------------|---------------------|  
|TRUE|ACTIVADA|Generar UNG|  
|TRUE|DESACTIVADA|Generar UNG|  
|FALSE|ACTIVADA|No generar UNG|  
|FALSE|DESACTIVADA|No generar UNG|  
|No está presente (OverrideEDIHeader es false)|ACTIVADA|Generar UNG|  
|No está presente (OverrideEDIHeader es false)|DESACTIVADA|No generar UNG|  
  
### <a name="group-envelopes"></a>Sobres de grupo  
 Los sobres de grupo presentan un desafío especial, dado que el intercambio puede tener presente más de un grupo. Para solucionar este problema, la canalización de envío EDI puede aplicar el sobre a todos los grupos del intercambio o aplicar el sobre al único grupo del intercambio.  
  
 Para las transacciones únicas se pueden invalidar todos los campos GS o UNG; para los intercambios por lotes solo se pueden invalidar los campos siguientes:  
  
-   GS04  
  
-   GS05  
  
-   UNG4_1  
  
-   UNG4_2  
  
### <a name="batching"></a>Procesar por lotes  
 La orquestación de procesamiento por lotes controla la invalidación del número de control de conjunto de transacciones para los mensajes por lotes. Las siguientes propiedades se pueden escribir en el contexto de cualquier mensaje que se procesará por lotes para invalidar el número de control de conjunto de transacciones:  
  
-   ST02 (para los mensajes X12)  
  
-   UNH1 (Para los mensajes EDIFACT)  
  
> [!NOTE]
>  Si varios mensajes entrantes contienen el mismo número de control en el mismo grupo, se suspenderán los mensajes con números duplicados.  
  
> [!NOTE]
>  No promocione las propiedades del contexto EdiOverride ISA, UNA, GS o UNG para los mensajes que van a procesarse por lotes. Si necesita invalidar estas propiedades, promociónelas en el mensaje de salida de la orquestación del lote antes de realizar el envío a la canalización de envío EDI.  
  
### <a name="delimiter-collision"></a>Colisión de delimitadores  
 Los delimitadores, como los encabezados UNA, deben contener un valor único para cada campo. Al invalidar los valores de los delimitadores, como los encabezados UNA, debe asegurarse de que cada valor de delimitador es único, no solo dentro de los valores que invalida, sino también entre cualquier valor de delimitador utilizado desde la configuración del acuerdo o el acuerdo de reserva.  
  
 Por ejemplo, si invalida UNA1, UNA2 y UNA4, y UNA3, UNA5, UNA6 y UNA6Suffix proceden de las propiedades del acuerdo, cada propiedad debe contener un valor único comparada con las demás.  
  
## <a name="see-also"></a>Vea también  
 [Cómo BizTalk Server envía mensajes EDI](../core/how-biztalk-server-sends-edi-messages.md)