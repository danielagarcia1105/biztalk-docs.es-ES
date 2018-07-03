---
title: Probar los esquemas | Microsoft Docs
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
ms.openlocfilehash: fc036be84bb64e794e6109e1ebc4ec730f382878
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023114"
---
# <a name="testing-schemas"></a>Probar los esquemas
Una vez creado un esquema, es probable que desee validar que éste describe la estructura XML que pretende describir. Puede realizar las tres operaciones siguientes en el esquema para validarlo:  
  
- **Generación de instancia**. esta operación genera un mensaje de instancia a partir de un esquema y crea los datos de prueba que se acompañan a los elementos y atributos XML especificados por el esquema.  
  
- **Validación de esquema**. esta operación valida la coherencia interna de un esquema y garantiza que se ajusta al estándar de esquema del lenguaje de definición de esquemas XML (XSD).  
  
- **Validación de instancia**. esta operación valida un determinado mensaje de instancia con respecto a un esquema.  
  
  Las tres operaciones son útiles para probar los esquemas antes de colocarlos en un entorno de producción para su uso.  
  
  Esta sección describe estas operaciones con mayor detalle.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo validar esquemas en Visual Studio](../core/how-to-validate-schemas-in-visual-studio.md)  
  
-   [Cómo validar los mensajes de instancia](../core/how-to-validate-instance-messages.md)  
  
-   [Cómo generar mensajes de instancia](../core/how-to-generate-instance-messages.md)