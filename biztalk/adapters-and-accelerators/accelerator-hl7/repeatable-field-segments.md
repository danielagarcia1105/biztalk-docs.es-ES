---
title: Segmentos de campo repetibles | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- segments, repeatable fields
- QPD
- Table Row Data (RDT)
- Query Parameter Definition (QPD)
- Segments table
- RDT
ms.assetid: 4c31cb56-21e5-4918-aaf6-67e8ceddd74f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9651b8d3414f792b81633cafbe41dd66559df04c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981981"
---
# <a name="repeatable-field-segments"></a>Segmentos de campo repetibles
La tabla de segmentos en la base de datos de Access de HL7 contiene una columna para el último campo de segmentos (ADD, RDT y QPD) dicho Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) se define como repetible (**Last_field_repeatable**  =  **True**). [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] no se admite agregar. Sin embargo, RDT y QPD están presentes en las tablas de consulta y responden con valores de tabla. El ejemplo siguiente se muestra cómo [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] controla estas columnas.  
  
 Un cliente envía la consulta siguiente e indica que el cliente desea recibir una respuesta inmediata estableciendo **prioridad RCP-1-Response** a "**me**":  
  
```  
MSH|^&~\|PCR|Gen Hosp|PIMS||199811201400-0800||QBP^Q42^QBP_Q13|ACK9901|P|2.4||||||||  
QPD|Q42^Tabular Dispense History^HL7nnn|Q0010|555444222111^^^MPI^MR| |19980531|19990531|  
RCP|I|999^RD|  
RDF|3|PatientList^ST^20~PatientName^XPN^48~MedicationDispensed^ST^40~RXD.3^TS^26  
```  
  
 El servidor responde a un minuto más tarde con el siguiente mensaje:  
  
```  
MSH|^&~\|PIMS|Gen Hosp|PCR||199811201401-0800||RTB^K42^RTB_K13|8858|P|2.3||||||||  
MSA|AA|8699|  
QAK|Q010|OK|Q42^Tabular Dispense History^HL7nnn|4  
QPD|Q42^Tabular Dispense History^HL7nnn|Q0010|555444222111^^^MPI^MR||19980531|19990531|  
RDF|7|PatientId^CX^20~PatientName^XPN^48~OrderControlCode^ID^2~ MedicationDispensed^CE^100~DispenseDate^TS^26~QuantityDispensed^NM^20~ OrderingProvider^XCN^120  
RDT|555444222111^^^MPI^MR|Everyman^Adam|RE|525440345^Verapamil Hydrochloride 120 mg TAB^NDC |199805291115-0700|100|77^Hippocrates^Harold^H^III^DR^MD  
RDT|555444222111^^^MPI^MR|Everyman^Adam|RE|00182196901^VERAPAMIL HCL ER TAB 180MG ER^NDC |19980821-0700|100|77^Hippocrates^Harold^H^III^DR^MD  
RDT|555444222111^^^MPI^MR|Everyman^Adam|RE|00172409660^BACLOFEN 10MG TABS^NDC |199809221415-0700|10|88^Semmelweis^Samuel^^^DR^MD  
RDT|555444222111^^^MPI^MR|Everyman^Adam|RE|00054384163^THEOPHYLLINE 80MG/15ML SOLN^NDC|199810121145-0700|10|99^Lister^Lenora^^^DR^MD  
```  
  
 En el ejemplo, verá que QPD y RDT son personalizados o definido por el sitio. La especificación de HL7 define QPD y RDT segmentos como sigue.  
  
## <a name="qpd---query-parameter-definition"></a>QPD - definición de parámetro de consulta  
 En la tabla siguiente se muestra cómo la especificación de HL7 define QPD.  
  
|SEQ|LEN|DT|PARTICIPAR|RP / #|TBL #|ELEMENTO #|NOMBRE DEL ELEMENTO|  
|---------|---------|--------|---------|------------|-----------|------------|------------------|  
|1|250|CE|R||0471|01375|Nombre de la consulta de mensaje|  
|2|32|ST|C|||00696|Etiqueta de consulta|  
|3-n|256|Varía||||01435|Parámetros de usuario en sucesivas campos|  
  
## <a name="rdt---table-row-data"></a>RDT - datos de la fila de tabla  
 En la tabla siguiente se muestra cómo la especificación de HL7 define RDT.  
  
|SEQ|LEN|DT|PARTICIPAR|RP / #|TBL #|ELEMENTO #|NOMBRE DEL ELEMENTO|  
|---------|---------|--------|---------|------------|-----------|------------|------------------|  
|1-n|Variable|Variable|R|||00703|Valor de columna|  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] interpreta QPD y RDT como valores definidos por el sitio que se pueden repetir. Puesto que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] no soluciona los tipos de datos y otros detalles, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] trata QPD.3 y RDT.1 como tipos de datos de cadena en los esquemas. Es posible que deba modificar estos esquemas según las condiciones de su propio sitio.  
  
## <a name="see-also"></a>Vea también  
 [Uso de esquemas HL7 2.X](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)