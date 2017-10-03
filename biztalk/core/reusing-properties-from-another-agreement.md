---
title: Volver a usar propiedades de otro acuerdo | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d8e1cc60-d581-43ca-aa70-1e0d6238497a
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e2a4e1efbfb7a86c18fb3643a789312a3707a72
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="reusing-properties-from-another-agreement"></a>Volver a usar propiedades de otro acuerdo
Se pueden reusar propiedades entre acuerdos. De este modo, ahorrará tiempo cuando la mayoría o todas las propiedades de un acuerdo nuevo son las mismas que las de un acuerdo que ya existe. La interfaz de usuario [!INCLUDE[firstref_TPM](../includes/firstref-tpm-md.md)] en [!INCLUDE[prague](../includes/prague-md.md)] permite exportar un acuerdo a un archivo de plantilla XML. A continuación, puede importar la plantilla XML para reusar las mismas propiedades de acuerdo.  
  
 La exportación de un acuerdo a una plantilla XML captura la mayoría de propiedades del acuerdo, pero no todas. Las siguientes propiedades *no* exportarán al archivo de plantilla XML:  
  
-   Todas las propiedades de la **propiedades generales** página en el **General** ficha.  
  
-   Todas las propiedades de la **contactos** página en el **General** ficha.  
  
-   Todas las propiedades de la **propiedades adicionales** página en el **General** ficha.  
  
-   Configuración relacionada con el identificador de la **identificadores** página de la ficha de acuerdo unidireccional. Los enfoques son:  
  
    -   **Para X12**: ISA5, ISA6, ISA7, ISA8 y la configuración de resolución de acuerdo adicional  
  
    -   **Para EDIFACT**: UNB 2.1, UNB 2.2, UNB 3.1, UNB 3.2 y configuración de resolución de acuerdo adicional  
  
    -   **Para AS2**: AS2-To, AS2-From y la configuración de resolución de acuerdo adicional  
  
-   La asociación de puerto de envío el **puertos de envío** página en la ficha de acuerdo unidireccional para X12, EDIFACT y AS2 contratos.  
  
 Aparte de las propiedades enumeradas arriba, las siguientes propiedades se exportarán al archivo de plantilla XML:  
  
-   Toda la configuración relacionada con el protocolo de codificación (X12, EDIFACT o AS2).  
  
-   Toda la configuración relacionada con el proceso por lotes (excepto el ID de lote).  
  
> [!NOTE]
>  Se sobrescribirán todas las propiedades aplicables al copiar propiedades en el acuerdo de destino.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Exportar las propiedades de acuerdo a un archivo XML](../core/exporting-agreement-properties-to-an-xml-file.md)  
  
-   [Propiedades del acuerdo de importación de un archivo XML](../core/importing-agreement-properties-from-an-xml-file.md)  
  
## <a name="see-also"></a>Vea también  
 [Configurar propiedades de EDI](../core/configuring-edi-properties.md)