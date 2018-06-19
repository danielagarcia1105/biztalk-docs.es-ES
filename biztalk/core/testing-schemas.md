---
title: Comprobación de esquemas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2e28b7c-9d0c-4336-8bee-4599d41a57f4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20879925ff98d5c5d6ca7d0c9ebcf11853239bba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279588"
---
# <a name="testing-schemas"></a>Comprobación de esquemas
Una vez creado un esquema, es probable que desee validar que éste describe la estructura XML que pretende describir. Puede realizar las tres operaciones siguientes en el esquema para validarlo:  
  
-   **Generación de instancia**. esta operación genera un mensaje de instancia a partir de un esquema y crea los datos de prueba que se acompañan a los elementos y atributos XML especificados por el esquema.  
  
-   **La validación del esquema**. esta operación valida la coherencia interna de un esquema y garantiza que se ajusta al estándar de esquema del lenguaje de definición de esquemas XML (XSD).  
  
-   **Validación de instancia**. esta operación valida un determinado mensaje de instancia con respecto a un esquema.  
  
 Las tres operaciones son útiles para probar los esquemas antes de colocarlos en un entorno de producción para su uso.  
  
 Esta sección describe estas operaciones con mayor detalle.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo validar esquemas en Visual Studio](../core/how-to-validate-schemas-in-visual-studio.md)  
  
-   [Cómo validar los mensajes de instancia](../core/how-to-validate-instance-messages.md)  
  
-   [Cómo generar mensajes de instancia](../core/how-to-generate-instance-messages.md)