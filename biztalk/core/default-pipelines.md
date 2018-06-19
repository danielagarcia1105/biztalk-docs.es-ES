---
title: Predeterminado canalizaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, PassThruTransmit
- pipelines, PassThruReceive
- pipelines, XMLTransmit
- pipelines, StsReceive
- pipelines, StsSend
- pipelines, StsFileReceive
- Microsoft.BizTalk.KwTpm.StsDefaultPipelines.EnvSchema XML envelope
- pipelines, XMLReceive
- pipelines, backward compatibility
- Microsoft.BizTalk.DefaultPipelines assembly
- pipelines, default
ms.assetid: 7d82bb2c-c7f1-44a1-9e1b-89b0bb806845
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ceb3f06f2e2b57ec37bc4a95a385574de594940
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239308"
---
# <a name="default-pipelines"></a>Canalizaciones predeterminadas
Cuando crea una nueva aplicación, las canalizaciones predeterminadas se crean e implementan de forma predeterminada y aparecen en el ensamblado Microsoft.BizTalk.DefaultPipelines, en la carpeta \References, de todos los proyectos de BizTalk. Las canalizaciones predeterminadas no pueden modificarse en el Diseñador de canalizaciones. Estas canalizaciones se pueden seleccionar al configurar un puerto de envío o una ubicación de recepción en el Explorador de BizTalk. En este tema se describen  las canalizaciones predeterminadas y cuándo deben utilizarse.  
  
> [!NOTE]
>  Las canalizaciones de recepción XML y de envío XML no admiten documentos XML de más de 4 gigabytes.  
  
## <a name="passthrureceive-pipeline"></a>Canalización PassThruReceive  
 La canalización de recepción de paso a través no tiene componentes. Se utiliza para escenarios de paso a través simples cuando no es necesario ningún procesamiento de carga de mensaje. Esta canalización se utiliza generalmente cuando se conocen el origen y el destino del mensaje y éste no requiere validación, codificación o desensamblado. Esta canalización suele utilizarse conjuntamente con la canalización de envío de paso a través.  
  
 Dado que no contiene un desensamblador, la canalización de recepción de paso a través no puede ser utilizada para enrutar mensajes hacia orquestaciones.  
  
> [!NOTE]
>  La canalización de recepción de paso a través no admite promoción de propiedad.  
  
## <a name="passthrutransmit-pipeline"></a>Canalización PassThruTransmit  
 La canalización de envío de paso a través no tiene componentes. Esta canalización se utiliza generalmente cuando no es necesario procesar documentos antes de enviar el mensaje a un destino.  
  
## <a name="xmlreceive-pipeline"></a>Canalización XMLReceive  
 La canalización de recepción XML consta de las siguientes fases:  
  
-   **Descodificar.** Vacía  
  
-   **Desensamblar.** Contiene el componente de desensamblador XML  
  
-   **Validar.** Vacía  
  
-   **ResolveParty.** Ejecute el componente de resolución de entidades, que resuelve el sujeto del certificado o el Id. de seguridad del remitente para el Id. de entidad.  
  
## <a name="xmltransmit-pipeline"></a>Canalización XMLTransmit  
 La canalización de envío XML consta de las siguientes fases:  
  
-   **Preensamblar.** Vacía  
  
-   **Ensamblar.** Contiene el componente de ensamblador XML  
  
-   **Codificar.** Vacía  
  
## <a name="see-also"></a>Vea también  
 [Tipos de canalizaciones](../core/types-of-pipelines.md)   
 [Tipos de componentes de canalización](../core/types-of-pipeline-components.md)   
 [Plantillas de canalización](../core/pipeline-templates.md)   
 [Componentes de canalización](../core/pipeline-components.md)   
 [Acerca de las canalizaciones, fases y componentes](../core/about-pipelines-stages-and-components.md)