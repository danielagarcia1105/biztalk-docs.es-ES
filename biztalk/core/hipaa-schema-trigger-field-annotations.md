---
title: Anotaciones de campo desencadenador HIPAA esquema | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e1389284-a2ec-44e7-a2f1-8d26f83fd31d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8c50db43b14899439877fde8ce0ee476feb5095
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="hipaa-schema-trigger-field-annotations"></a><span data-ttu-id="cff14-102">Anotaciones del campo desencadenador del esquema HIPAA</span><span class="sxs-lookup"><span data-stu-id="cff14-102">HIPAA Schema Trigger Field Annotations</span></span>
<span data-ttu-id="cff14-103">Los segmentos EDI contienen con frecuencia valores de calificador que modifican el significado del segmento.</span><span class="sxs-lookup"><span data-stu-id="cff14-103">EDI segments often contain qualifier values that modify the meaning of the segment.</span></span> <span data-ttu-id="cff14-104">Por ejemplo, el segmento N1 puede contener un elemento calificador “BT” para indicar “bill-to name” o puede contener un elemento calificador “ST” para indicar “ship-to name”.</span><span class="sxs-lookup"><span data-stu-id="cff14-104">For example, an N1 segment can contain a qualifying element of “BT” to signify a “bill-to name,” or it may contain a qualifying element of “ST” to indicate a “ship-to name.”</span></span> <span data-ttu-id="cff14-105">Normalmente, se deja a la lógica de negocios para determinar cómo interpretar estos campos y el Desensamblador resuelve todas las instancias del segmento N1 en el mismo nombre de registro XML; Sin embargo, los esquemas HIPAA incluidos con BizTalk Server contienen anotaciones que permiten el Desensamblador EDI cree registros XML únicos basados en la presencia de un elemento de calificación.</span><span class="sxs-lookup"><span data-stu-id="cff14-105">Normally it is left to business logic to determine how to interpret these fields and the disassembler resolves all instances of the N1 segment to the same XML record name; however, the HIPAA schemas shipped with BizTalk Server contain annotations that allow the EDI disassembler to create unique XML records based on the presence of a qualifying element.</span></span>  
  
 <span data-ttu-id="cff14-106">**Implementación del campo desencadenador**</span><span class="sxs-lookup"><span data-stu-id="cff14-106">**Trigger Field Implementation**</span></span>  
  
 <span data-ttu-id="cff14-107">Los campos desencadenadores se implementan como un par de atributos XML que describen el elemento de segmento y el valor de desencadenador que causa este registro que se cree.</span><span class="sxs-lookup"><span data-stu-id="cff14-107">Trigger fields are implemented as a pair of XML attributes that describe the segment element and the trigger value that causes this record to be created.</span></span> <span data-ttu-id="cff14-108">En la tabla siguiente se describen los atributos:</span><span class="sxs-lookup"><span data-stu-id="cff14-108">The following table describes these attributes:</span></span>  
  
|<span data-ttu-id="cff14-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="cff14-109">Attribute</span></span>|<span data-ttu-id="cff14-110">Finalidad</span><span class="sxs-lookup"><span data-stu-id="cff14-110">Purpose</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="cff14-111">trigger_field</span><span class="sxs-lookup"><span data-stu-id="cff14-111">trigger_field</span></span>|<span data-ttu-id="cff14-112">El campo de segmento en el que se buscará el valor desencadenador.</span><span class="sxs-lookup"><span data-stu-id="cff14-112">The segment field that will be inspected for the trigger value.</span></span>|  
|<span data-ttu-id="cff14-113">trigger_value</span><span class="sxs-lookup"><span data-stu-id="cff14-113">trigger_value</span></span>|<span data-ttu-id="cff14-114">Los valores desencadenadores.</span><span class="sxs-lookup"><span data-stu-id="cff14-114">The trigger value(s).</span></span><br /><br /> <span data-ttu-id="cff14-115">Puede contener un único valor o una lista de valores delimitados por espacios.</span><span class="sxs-lookup"><span data-stu-id="cff14-115">This may contain a single value, or a space delimited list of values.</span></span>|  
  
 <span data-ttu-id="cff14-116">En la tabla siguiente se muestra la anotación de desencadenador tal como aparecería en el esquema HIPAA, el segmento EDI que causará que se active el desencadenador y los datos XML resultantes después del procesamiento del segmento.</span><span class="sxs-lookup"><span data-stu-id="cff14-116">The following table shows the trigger annotation as it would appear in the HIPAA schema, the EDI segment that will cause the trigger to activate, and the resulting XML data after processing the segment.</span></span>  
  
|<span data-ttu-id="cff14-117">Anotación de desencadenador de esquema</span><span class="sxs-lookup"><span data-stu-id="cff14-117">Schema Trigger Annotation</span></span>|<span data-ttu-id="cff14-118">Segmento de N1 coincidente</span><span class="sxs-lookup"><span data-stu-id="cff14-118">Matching N1 Segment</span></span>|<span data-ttu-id="cff14-119">Datos XML resultantes</span><span class="sxs-lookup"><span data-stu-id="cff14-119">Resulting XML Data</span></span>|  
|-------------------------------|-------------------------|------------------------|  
|`<xs:element name="TS835W1_1000A_Loop">  <xs:annotation>   <xs:appinfo>    <b:recordInfo structure="delimited" delimiter_type="inherit_record"     field_order="infix" count_ignore="yes" child_delimiter="default"     trigger_field="N1_PayerIdentification_TS835W1_1000A/N101__EntityIdentifierCode"     trigger_value="PR" notes="Payer Identification" />    </xs:appinfo>  </xs:annotation>`|<span data-ttu-id="cff14-120">N1 * PR\*Contoso\*XV\*0000000 ~</span><span class="sxs-lookup"><span data-stu-id="cff14-120">N1*PR\*Contoso\*XV\*0000000~</span></span>|`<ns0:TS835W1_1000A_Loop>  <N1_PayerIdentification_TS835W1_1000A>   <N101__EntityIdentifierCode>PR</N101__EntityIdentifierCode>    <N102__PayerName>Contoso</N102__PayerName>    <N103__IdentificationCodeQualifier>XV</N103__IdentificationCodeQualifier>    <N104__PayerIdentifier>0000000</N104__PayerIdentifier>   </N1_PayerIdentification_TS835W1_1000A>`|  
|`<xs:element name="TS835W1_1000B_Loop">   <xs:annotation>    <xs:appinfo>     <b:recordInfo structure="delimited" delimiter_type="inherit_record"     field_order="infix" count_ignore="yes" child_delimiter="default"     trigger_field="N1_PayeeIdentification_TS835W1_1000B/N101__EntityIdentifierCode"     trigger_value="PE" notes="Payee Identification" />    </xs:appinfo>   </xs:annotation>`|<span data-ttu-id="cff14-121">N1 * PE\*Fabrikam\*FI\*9999999 ~</span><span class="sxs-lookup"><span data-stu-id="cff14-121">N1*PE\*Fabrikam\*FI\*9999999~</span></span>|`<TS835W1_1000B_Loop>   <N1_PayeeIdentification_TS835W1_1000B>    <N101__EntityIdentifierCode>PE</N101__EntityIdentifierCode>    <N102__PayeeName>Fabrikam</N102__PayeeName>    <N103__IdentificationCodeQualifier>FI</N103__IdentificationCodeQualifier>    <N104__PayeeIdentificationCode>9999999</N104__PayeeIdentificationCode>   </N1_PayeeIdentification_TS835W1_1000B>`|  
  
 <span data-ttu-id="cff14-122">**Procesamiento de desensamblador EDI de campos de desencadenador**</span><span class="sxs-lookup"><span data-stu-id="cff14-122">**EDI Disassembler Processing of Trigger Fields**</span></span>  
  
 <span data-ttu-id="cff14-123">Cuando se recibe un conjunto de transacciones HIPAA, si el desensamblador EDI encuentra un segmento que contiene un campo desencadenador, usa la información de desencadenador para generar un registro XML específico para la combinación de segmento y desencadenador.</span><span class="sxs-lookup"><span data-stu-id="cff14-123">When receiving a HIPAA transaction set, if the EDI disassembler encounters a segment that contains a trigger field, it uses the trigger information to generate an XML record specific to the segment and trigger combination.</span></span> <span data-ttu-id="cff14-124">Por ejemplo, en los datos EDI siguientes, hay dos segmentos N1 que tienen diferentes valores para N101, PR y PE:</span><span class="sxs-lookup"><span data-stu-id="cff14-124">For example, in the following EDI data, there are two N1 segments that have different values for N101, PR and PE:</span></span>  
  
```  
  
N1*PR*Contoso*XV*0000000~  
N3*N301__PayerAddressLine~  
N4*N401__PayerCityName*N4*N403__PayerPost**N4*N406~  
……  
N1*PE*Fabrikam*FI*9999999~  
N3*N301__PayeeAddressLine~  
N4*N401__PayeeCityName*N4*N403__PayeePost**N4*N406~  
  
```  
  
 <span data-ttu-id="cff14-125">Cuando se procesa el Desensamblador EDI, las anotaciones de campo desencadenador presentes en el esquema producirá dos registros XML independientes basados en el valor de N101, < N1_PayerIdentification_TS835W1_1000A > y < N1_PayeeIdentification_TS835W1_1000B >, correspondientes a N1 * PR y N1\*PE.</span><span class="sxs-lookup"><span data-stu-id="cff14-125">When processed by the EDI disassembler, the trigger field annotations present in the schema will result in two separate XML records based on the value of N101, <N1_PayerIdentification_TS835W1_1000A> and <N1_PayeeIdentification_TS835W1_1000B>, corresponding to N1*PR and N1\*PE.</span></span>  
  
 <span data-ttu-id="cff14-126">Cuando se realiza el envío, el ensamblador EDI eliminará el sufijo después del carácter “_” para los campos que contengan una anotación de desencadenador.</span><span class="sxs-lookup"><span data-stu-id="cff14-126">When sending, the EDI assembler will drop the suffix following the “_” character for fields that contain a trigger annotation.</span></span> <span data-ttu-id="cff14-127">Por ejemplo, <N1_PayerIdentification_TS835W1_1000A> y <N1_PayeeIdentification_TS835W1_1000B> se convertirán en N1.</span><span class="sxs-lookup"><span data-stu-id="cff14-127">For example, both <N1_PayerIdentification_TS835W1_1000A> and <N1_PayeeIdentification_TS835W1_1000B> will both become N1.</span></span>  
  
 <span data-ttu-id="cff14-128">**Segmentos predeterminados y campos desencadenadores**</span><span class="sxs-lookup"><span data-stu-id="cff14-128">**Default Segments and Trigger Fields**</span></span>  
  
 <span data-ttu-id="cff14-129">En la tabla siguiente contiene información sobre los segmentos predeterminados y campos de desencadenador que se usan en documentos HIPAA suministrados como parte de BizTalk Server:</span><span class="sxs-lookup"><span data-stu-id="cff14-129">The following table contains information on the default segments and trigger fields used in HIPAA documents supplied as part of BizTalk Server:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cff14-130">Los valores desencadenadores individuales que se usan con los campos desencadenadores pueden variar entre esquemas.</span><span class="sxs-lookup"><span data-stu-id="cff14-130">The individual trigger values used with the trigger fields may vary between schemas.</span></span>  
  
|<span data-ttu-id="cff14-131">Segmento con desencadenador</span><span class="sxs-lookup"><span data-stu-id="cff14-131">Segment with Trigger</span></span>|<span data-ttu-id="cff14-132">Campo desencadenador</span><span class="sxs-lookup"><span data-stu-id="cff14-132">Trigger field</span></span>|  
|--------------------------|-------------------|  
|<span data-ttu-id="cff14-133">AMT</span><span class="sxs-lookup"><span data-stu-id="cff14-133">AMT</span></span>|<span data-ttu-id="cff14-134">AMT01</span><span class="sxs-lookup"><span data-stu-id="cff14-134">AMT01</span></span>|  
|<span data-ttu-id="cff14-135">CRC</span><span class="sxs-lookup"><span data-stu-id="cff14-135">CRC</span></span>|<span data-ttu-id="cff14-136">CRC01</span><span class="sxs-lookup"><span data-stu-id="cff14-136">CRC01</span></span>|  
|<span data-ttu-id="cff14-137">DTM</span><span class="sxs-lookup"><span data-stu-id="cff14-137">DTM</span></span>|<span data-ttu-id="cff14-138">DTM01</span><span class="sxs-lookup"><span data-stu-id="cff14-138">DTM01</span></span>|  
|<span data-ttu-id="cff14-139">DTP</span><span class="sxs-lookup"><span data-stu-id="cff14-139">DTP</span></span>|<span data-ttu-id="cff14-140">DTP01</span><span class="sxs-lookup"><span data-stu-id="cff14-140">DTP01</span></span>|  
|<span data-ttu-id="cff14-141">ENT</span><span class="sxs-lookup"><span data-stu-id="cff14-141">ENT</span></span>|<span data-ttu-id="cff14-142">ENT02</span><span class="sxs-lookup"><span data-stu-id="cff14-142">ENT02</span></span>|  
|<span data-ttu-id="cff14-143">HI</span><span class="sxs-lookup"><span data-stu-id="cff14-143">HI</span></span>|<span data-ttu-id="cff14-144">HI01:01</span><span class="sxs-lookup"><span data-stu-id="cff14-144">HI01:01</span></span>|  
|<span data-ttu-id="cff14-145">N1</span><span class="sxs-lookup"><span data-stu-id="cff14-145">N1</span></span>|<span data-ttu-id="cff14-146">N101</span><span class="sxs-lookup"><span data-stu-id="cff14-146">N101</span></span>|  
|<span data-ttu-id="cff14-147">NM1</span><span class="sxs-lookup"><span data-stu-id="cff14-147">NM1</span></span>|<span data-ttu-id="cff14-148">NM01</span><span class="sxs-lookup"><span data-stu-id="cff14-148">NM01</span></span>|  
|<span data-ttu-id="cff14-149">NTE</span><span class="sxs-lookup"><span data-stu-id="cff14-149">NTE</span></span>|<span data-ttu-id="cff14-150">NTE01</span><span class="sxs-lookup"><span data-stu-id="cff14-150">NTE01</span></span>|  
|<span data-ttu-id="cff14-151">REF</span><span class="sxs-lookup"><span data-stu-id="cff14-151">REF</span></span>|<span data-ttu-id="cff14-152">REF01</span><span class="sxs-lookup"><span data-stu-id="cff14-152">REF01</span></span>|  
|<span data-ttu-id="cff14-153">RMR</span><span class="sxs-lookup"><span data-stu-id="cff14-153">RMR</span></span>|<span data-ttu-id="cff14-154">RMR01</span><span class="sxs-lookup"><span data-stu-id="cff14-154">RMR01</span></span>|