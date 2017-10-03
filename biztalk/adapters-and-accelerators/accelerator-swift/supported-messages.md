---
title: Admite mensajes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SWIFT messages, supported message types
ms.assetid: 9e059f86-05b1-4c6b-afa8-0ca969874a97
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb5f4f38b347f89a3272fd9476e6e3878e2701ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="supported-messages"></a>Mensajes compatibles
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] proporciona una lista de [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] y los mensajes de SWIFT. Los mensajes se dividen en varias categorías financieros que se enumeran a continuación.  
  
 Esta sección contiene:  
  
-   [Mensajes de SWIFT - Microsoft](#fsa_intro_xtkj)  
  
-   [Categoría 0: Mensajes del sistema FIN](#fsa_intro_xcpk)  
  
-   [Categoría 1: Los pagos del cliente y comprobaciones](#fsa_intro_lxnf)  
  
-   [Categoría 2: Las transferencias de institución financiera](#fsa_intro_fywg)  
  
-   [Categoría 3: Tesoro mercados Exchange externa, mercados de dinero y derivados](#fsa_intro_qipa)  
  
-   [Categoría 4: Colecciones y letras efectivo](#fsa_intro_ruuc)  
  
-   [Categoría 5: Los mercados de valores](#fsa_intro_iitn)  
  
-   [Categoría 6: Tesoro comercializa preciosos metal](#fsa_intro_bjez)  
  
-   [Categoría 7: Créditos documentales y las garantías](#fsa_intro_vhkw)  
  
-   [Categoría 8: Viajeros Cheques](#fsa_intro_qlwo)  
  
-   [Categoría 9: Estado de cliente y la gestión de efectivo](#fsa_intro_sptj)  
  
##  <a name="fsa_intro_xtkj"></a>Mensajes de SWIFT - Microsoft  
 La tabla siguiente se describen los [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] mensajes SWIFT para tipos de servicio GPA y Control de FIN.  
  
|Tipo de mensaje|Description|  
|------------------|-----------------|  
|**02**|Mensaje de solicitud de inicio de sesión|  
|**03**|Seleccione el comando|  
|**05**|Quit, comando|  
|**06**|Comando de cierre de sesión|  
|**12**|Solicitud del sistema Remove Asia Pacífico|  
|**13**|Confirmación de Asia Pacífico de anulación de sistema|  
|**14**|Solicitud del sistema para quitar LT|  
|**15**|Confirmación de sistema de anulación LT iniciada por el usuario|  
|**21**|Confirmación de un mensaje de GPA enviado por un LT (confirmación/NAK)|  
|**21**|Confirmación de un mensaje de GPA recibido por un LT (confirmación/NAK)|  
|**21**|Confirmación de un mensaje FIN enviado por un LT (confirmación/NAK)|  
|**21**|Confirmación de un mensaje FIN recibido por un LT (UAK/UNK)|  
|**22**|Inicio de sesión una confirmación positiva (LAK)|  
|**23**|Confirmación de una solicitud de Select (SAK)|  
|**25**|Salga de confirmación|  
|**26**|Confirmación de cierre de sesión|  
|**33**|Solicitud de usuario anulación Asia Pacífico|  
|**35**|Solicitud del usuario para anular LT (anulación LT)|  
|**42**|Confirmación de inicio de sesión que no (LNK)|  
|**43**|Seleccione una confirmación negativa (SNK)|  
  
##  <a name="fsa_intro_xcpk"></a>Categoría 0: Mensajes del sistema FIN  
 En la tabla siguiente describe la forma de mensajes categoría 0: financieros mensajes del sistema, incluidos los usuarios puedan SWIFT y SWIFT al usuario.  
  
|Tipo de mensaje|Description|  
|------------------|-----------------|  
|**MT 008**|Solicitud del sistema para salir|  
|**MT 009**|Solicitud de cierre de sesión del sistema|  
|**MT 010**|Advertencia de no entrega|  
|**MT 011**|Notificación de entrega|  
|**MT 012**|Notificación de remitente|  
|**MT 015**|NAK diferida|  
|**MT 019**|Anular la notificación|  
|**MT 020**|Solicitud de recuperación (texto e historial)|  
|**MT 021**|Mensaje recuperado (texto e historial)|  
|**MT 022**|Solicitud de recuperación (historial)|  
|**MT 023**|Mensaje recuperado (historial)|  
|**MT 028**|Solicitud de estado de mensaje de copia FIN|  
|**MT 029**|Informe de estado de mensaje de copia FIN|  
|**MT 031**|Solicitud de historial de sesión|  
|**MT 032**|Solicitud de estado de entrega subconjunto|  
|**MT 035**|Solicitud de instrucciones de entrega.|  
|**MT 036**|Solicitud de historial LT|  
|**MT 037**|Solicitud de estado de zona horaria|  
|**MT 041**|Seleccione la solicitud de estado de FIN|  
|**MT 042**|Corte veces la solicitud de lista|  
|**MT 043**|Solicitud de lista de días no laborables|  
|**MT 044**|Nueva definición de reglas de informe no entregado|  
|**MT 045**|Solicitud de cambio de tiempo de comprobación diaria|  
|**MT 046**|Solicitud de informe de mensaje no entregado|  
|**MT 047**|Solicitud de nueva definición de las instrucciones de entrega|  
|**MT 048**|Solicitud de reglas de informe no entregado|  
|**MT 049**|Consulta de tiempo de informe de comprobación diaria|  
|**MT 051**|Informe de historial de sesión|  
|**MT 052**|Informe de estado de entrega subconjunto|  
|**MT 055**|Informe de instrucciones de entrega|  
|**MT 056**|Informe de historial LT|  
|**MT 057**|Informe de estado de zona horaria|  
|**MT 061**|Seleccione el informe de estado para FINÉS|  
|**MT 062**|Informe de lista de la hora de finalización|  
|**MT 063**|Informe de lista de días no laborables|  
|**MT 064**|Informe de cambios de las reglas de informe no entregado|  
|**MT 065**|Informe de cambios de tiempo para el informe de comprobación de diario|  
|**MT 066**|Solicitado el informe de mensaje no entregado|  
|**MT 067**|Informe de redefinición de instrucciones de entrega|  
|**MT 068**|Reglas de informe no entregado|  
|**MT 069**|Estado de tiempo de informe de comprobación diaria|  
|**MT 072**|Selección del modo de prueba|  
|**MT 073**|Solicitud de ejemplo de mensaje|  
|**MT 074**|Solicitud de difusión|  
|**MT 075**|Solicitudes de certificación|  
|**MT 076**|Error de certificación|  
|**MT 077**|Criterios de selección adicionales de FIN|  
|**MT 081**|Informe de comprobación de diario|  
|**MT 082**|Informe de mensaje no entregado a una hora fija|  
|**MT 083**|Informe de mensaje no entregado en tiempo de corte|  
|**MT 085**|Información de entrega de ICC|  
|**MT 087**|Respuesta de certificación|  
|**MT 090**|Mensaje de usuario para SWIFT|  
|**MT 092**|Mensaje de usuario a SWIFT|  
|**MT 094**|Broadcast|  
|**MT 096**|Copia FIN al mensaje de la entidad Central|  
|**MT 097**|Notificación de autorización o denegación de mensaje de copia FIN|  
  
##  <a name="fsa_intro_lxnf"></a>Categoría 1: Los pagos del cliente y comprobaciones  
 En la tabla siguiente describe los mensajes de categoría 1: pagos y comprobaciones.  
  
|Tipo de mensaje|Description|  
|------------------|-----------------|  
|**MT 101**|Solicitud de transferencia|  
|**MT 102**|Transferencia de cliente múltiple|  
|**MT 102 +**|Transferencia de cliente múltiple (STP)|  
|**MT 103**|Transferencia de crédito de cliente único|  
|**MT 103 +**|Transferencia de crédito solo cliente (STP)|  
|**MT 104**|Adeudo directo y solicitud de débito de transferencia de mensajes|  
|**MT 105**|Sobre de EDIFACT|  
|**MT 106**|Sobre de EDIFACT|  
|**MT 107**|Mensaje de débito directo de general|  
|**MT 110**|Consejos de cheques|  
|**MT 111**|Solicitud para detener el pago de un Cheque|  
|**MT 112**|Estado de una solicitud para detener el pago de un Cheque|  
|**MT 121**|Transferencia de fondos de bancos vinculados varios (FINPAY de EDIFACT)|  
|**MT 190**|Consejos de cargos, interés y otros ajustes|  
|**MT 191**|Solicitud de pago de cargos, interés y otros gastos|  
|**MT 192**|Solicitud de cancelación|  
|**MT 195**|Consultas|  
|**MT 196**|Respuestas|  
|**MT 198**|Mensaje de propietario|  
|**MT 199**|Mensaje de formato libre|  
  
##  <a name="fsa_intro_fywg"></a>Categoría 2: Las transferencias de institución financiera  
 En la tabla siguiente describe los mensajes de la categoría 2: las transferencias de institución financiera.  
  
|Tipo de mensaje|Description|  
|------------------|-----------------|  
|**MT 200**|Transferencia de institución financiera por cuenta propia|  
|**MT 201**|Transferencia de varios institución financiera por cuenta propia|  
|**MT 202**|Transferencia de institución financiera general|  
|**MT 203**|Transferencia de varios institución financiera General|  
|**MT 204**|Mensaje de débito directo de los mercados financieros|  
|**MT 205**|Ejecución de transferencia institución financiera|  
|**MT 206**|Mensaje de truncamiento de cheque|  
|**MT 207**|Solicitud de transferencia de institución financiera|  
|**MT 210**|Aviso para recibir|  
|**MT 256**|Consejos de pago de Cheques|  
|**MT 290**|Consejos de cargos, interés y otros ajustes|  
|**MT 291**|Solicitud de pago de cargos, interés y otros gastos|  
|**MT 292**|Solicitud de cancelación|  
|**MT 293**|Mensaje de servicio de información|  
|**MT 295**|Consultas|  
|**MT 296**|Respuestas|  
|**MT 298**|Mensaje de propietario|  
|**MT 299**|Mensaje de formato libre|  
  
##  <a name="fsa_intro_qipa"></a>Categoría 3: Tesoro mercados Exchange externa, mercados de dinero y derivados  
 En la tabla siguiente describe los mensajes de la categoría 3: Tesoro mercados divisas, mercados de dinero y derivados.  
  
|Tipo de mensaje|Description|  
|------------------|-----------------|  
|**MT 300**|Confirmación de divisa extranjera|  
|**MT 303**|Instrucción de asignación de opción Forex/moneda|  
|**MT 304**|Consejos/instrucción de una solución de terceros|  
|**MT 305**|Confirmación de la opción de divisa extranjera|  
|**MT 306**|Confirmación de la opción de divisa extranjera|  
|**MT 307**|Consejos/instrucción de un acuerdo de FX de terceros|  
|**MT 308**|Instrucciones para liquidación bruta/neta de terceros FX acuerdos|  
|**MT 320**|Confirmación de depósito/préstamo fijo|  
|**MT 321**|Instrucciones para liquidar un préstamo/depósito de terceros|  
|**MT 330**|Llamada/aviso de confirmación de depósito/préstamo|  
|**MT 340**|Confirmación del acuerdo de velocidad hacia delante|  
|**MT 341**|Confirmación de liquidación de acuerdo de velocidad hacia delante|  
|**MT 350**|Consejos de pago de interés de préstamo/depósito|  
|**MT 360**|Confirmación derivado de moneda único tipo de interés|  
|**MT 361**|Entre la confirmación de intercambio de tipo de interés de moneda|  
|**MT 362**|Tipo de interés restablecimiento/consejos de pago|  
|**MT 364**|Confirmación de terminación/Recouponing de moneda única interés Swap|  
|**MT 365**|Cross moneda interés intercambio terminación/Recouponing confirmación|  
|**MT 380**|Orden de divisa extranjera|  
|**MT 381**|Confirmación de pedido de divisa extranjera|  
|**MT 390**|Consejos de cargos, interés y otros ajustes|  
|**MT 391**|Solicitud de pago de cargos, interés y otros gastos|  
|**MT 392**|Solicitud de cancelación|  
|**MT 395**|Consultas|  
|**MT 396**|Respuestas|  
|**MT 398**|Mensaje de propietario|  
|**MT 399**|Mensaje de formato libre|  
  
##  <a name="fsa_intro_ruuc"></a>Categoría 4: Colecciones y letras efectivo  
 En la tabla siguiente describe los mensajes de la categoría 4: colecciones y letras de efectivo.  
  
|Tipo de mensaje|Description|  
|------------------|-----------------|  
|**MT 400**|Consejos de pago|  
|**MT 405**|Limpiar la colección|  
|**MT 410**|Acknowledgement|  
|**MT 412**|Consejos de aceptación|  
|**MT 416**|Consejo de no-pago no de aceptación|  
|**MT 420**|Tracer|  
|**MT 422**|Consejos de alcance y solicitud de instrucciones|  
|**MT 430**|Modificación de instrucciones|  
|**MT 450**|Consejos de crédito de letra de efectivo|  
|**MT 455**|Consejos de ajuste de crédito de letra de efectivo|  
|**MT 456**|Consejos de Dishonour|  
|**MT 490**|Consejos de cargos, interés y otros ajustes|  
|**MT 491**|Solicitud de pago de cargos, interés y otros gastos|  
|**MT 492**|Solicitud de cancelación|  
|**MT 495**|Consultas|  
|**MT 496**|Respuestas|  
|**MT 498**|Mensaje de propietario|  
|**MT 499**|Mensaje de formato libre|  
  
##  <a name="fsa_intro_iitn"></a>Categoría 5: Los mercados de valores  
 En la tabla siguiente describe los mensajes de categoría 5: los mercados de valores.  
  
|Tipo de mensaje|Description|  
|------------------|-----------------|  
|**MT 500**|Instrucciones para el registro|  
|**MT 501**|Confirmación de registro o la modificación|  
|**MT 502**|Pedido de comprar o vender|  
|**MT 503**|Notificación colateral|  
|**MT 504**|Colateral propuesta|  
|**MT 505**|Sustitución colateral|  
|**MT 506**|Declaración de exposición y la documentación y material adjunto|  
|**MT 507**|Estado colateral y consejos de procesamiento|  
|**MT 508**|Posición dentro de un Consejo|  
|**MT 509**|Mensaje de estado de intercambios|  
|**MT 510**|Estado de registro y consejos de procesamiento|  
|**MT 513**|Consejos de cliente de ejecución|  
|**MT 514**|Instrucción de asignación de comercio|  
|**MT 515**|Confirmación de cliente de compra o venta|  
|**MT 516**|Confirmación de préstamo de valores|  
|**MT 517**|Afirmación de confirmación de comercio|  
|**MT 518**|Confirmación de comercio de títulos de lado de mercado|  
|**MT 519**|Modificación de detalles de cliente|  
|**MT 524**|Instrucción de posición dentro de un|  
|**MT 526**|Valores generales de préstamos/préstamo mensaje|  
|**MT 527**|Instrucción colateral Tri terceros|  
|**MT 528**|Instrucción etc. liquidación de cliente|  
|**MT 529**|Instrucción de liquidación de lado de mercado etc.|  
|**MT 530**|Comando de procesamiento de transacciones|  
|**MT 535**|Instrucción de explotaciones|  
|**MT 536**|Instrucción de transacciones|  
|**MT 537**|Instrucción de las transacciones pendientes|  
|**MT 538**|Instrucción de avisos de posición dentro de un|  
|**MT 540**|Recepción de forma gratuita|  
|**MT 541**|Recibir pagos|  
|**MT 542**|Entregar de forma gratuita|  
|**MT 543**|Entregar oneroso|  
|**MT 544**|Recibir confirmación libre|  
|**MT 545**|Recibir confirmación de pago|  
|**MT 546**|Entregar confirmación libre|  
|**MT 547**|Entregar en confirmación de pago|  
|**MT 548**|Estado de liquidación y consejos de procesamiento|  
|**MT 549**|Solicitud de Consejo de procesamiento de una instrucción /|  
|**MT 558**|Estado colateral Tri terceros y consejos de procesamiento|  
|**MT 559**|Notificación de agentes de pago|  
|**MT 564**|Notificación de acción corporativa|  
|**MT 565**|Instrucción de acción corporativa|  
|**MT 566**|Confirmación de acción corporativa|  
|**MT 567**|Estado de la acción corporativa y consejos de procesamiento|  
|**MT 568**|Acción corporativa Narrative|  
|**MT 569**|Declaración de exposición y Tri terceros documentación y material adjunto|  
|**MT 574**|(IRSLST) ANR IRS 1441|  
|**MT 574**|(W8BENO) ANR IRS 1441|  
|**MT 575**|Informe de actividad combinada|  
|**MT 576**|Instrucción de pedidos abiertos|  
|**MT 577**|Instrucción de números|  
|**MT 578**|Liquidación Allegement|  
|**MT 579**|Número de certificado|  
|**MT 581**|Mensaje de ajuste colateral|  
|**MT 582**|Notificación de reembolso o asesoramiento|  
|**MT 584**|Instrucción de etc. pendiente de transacciones|  
|**MT 586**|Instrucción de liquidación Allegements|  
|**MT 587**|Instrucción de recepción depositario|  
|**MT 588**|Confirmación de recepción de depositario|  
|**MT 589**|Estado de recepción de depositario y consejos de procesamiento|  
|**MT 590**|Consejos de cargos, interés y otros ajustes|  
|**MT 591**|Solicitud de pago de cargos, interés y otros gastos|  
|**MT 592**|Mensaje de usuario a SWIFT|  
|**MT 595**|Preguntas|  
|**MT 596**|Respuestas|  
|**MT 598**|Mensaje de propietario|  
|**MT 599**|Mensaje de formato libre|  
  
##  <a name="fsa_intro_bjez"></a>Categoría 6: Tesoro comercializa preciosos metal  
 En la tabla siguiente describe los mensajes de la categoría 6: Tesoro mercados preciosos metal, las sindicaciones de mercados de Tesoro y mensajes comunes de mercados de Tesoro.  
  
|Tipo de mensaje|Description|  
|------------------|-----------------|  
||**Tesoro comercializa preciosos metal**|  
|**MT 600**|Confirmación de comercio completa|  
|**MT 601**|Confirmación de la opción de sistema operativo preciosos|  
|**MT 604**|Orden de transferencia y entrega de sistema operativo preciosos|  
|**MT 605**|Aviso de sistema operativo preciosos para recibir|  
|**MT 606**|Sistema operativo preciosos débito consejos|  
|**MT 607**|Sistema operativo preciosos crédito consejos|  
|**MT 608**|Instrucción de una cuenta de sistema operativo|  
|**MT 609**|Instrucción de contratos de sistema operativo|  
|**MT 620**|Confirmación de metal préstamo fijo/ingreso|  
||**Tesoro comercializa las sindicaciones**|  
|**MT 643**|Aviso de reducción/renovación|  
|**MT 644**|Consejos de velocidad y corrección de cantidad|  
|**MT 645**|Aviso de cuota de vencimiento|  
|**MT 646**|Pago de entidad de seguridad o de interés|  
|**MT 649**|Mensaje de instalación sindicado general|  
||**Mercados Tesoro - mensajes comunes**|  
|**MT 690**|Consejos de cargos, interés y otros ajustes|  
|**MT 691**|Solicitud de pago de cargos, interés y otros gastos|  
|**MT 692**|Solicitud de cancelación|  
|**MT 695**|Consultas|  
|**MT 696**|Respuestas|  
|**MT 698**|Mensaje de propietario|  
|**MT 699**|Mensaje de formato libre|  
  
##  <a name="fsa_intro_vhkw"></a>Categoría 7: Créditos documentales y las garantías  
 En la tabla siguiente describe los mensajes de categoría 7: documental créditos y garantías.  
  
|Tipo de mensaje|Description|  
|------------------|-----------------|  
|**MT 700**|Problema de un crédito documental|  
|**MT 701**|Problema de un crédito documental|  
|**MT 705**|Consejos previa de un crédito documental|  
|**MT 707**|Modificación de un crédito documental|  
|**MT 710**|Consejos de un tercer crédito documental de bancos|  
|**MT 711**|Consejos de un tercer crédito documental de bancos|  
|**MT 720**|Transferencia de un crédito documental|  
|**MT 721**|Transferencia de un crédito documental|  
|**MT 730**|Acknowledgement|  
|**MT 732**|Consejos de descarga|  
|**MT 734**|Consejos de denegación|  
|**MT 740**|Autorización para reembolsar|  
|**MT 742**|Notificación de reembolso|  
|**MT 747**|Modificación de una autorización para reembolsar|  
|**MT 750**|Consejos de discrepancia|  
|**MT 752**|Autorización para pagar, acepte o negociar|  
|**MT 754**|Consejos de pago/aceptación/negociación|  
|**MT 756**|Consejos de reembolso o de pago|  
|**MT 760**|Garantía|  
|**MT 767**|Modificación de garantía|  
|**MT 768**|Confirmación de un mensaje de garantía|  
|**MT 769**|Consejos de reducción o versión|  
|**MT 790**|Consejos de cargos, interés y otros ajustes|  
|**MT 791**|Solicitud de pago de cargos, interés y otros gastos|  
|**MT 792**|Solicitud de cancelación|  
|**MT 795**|Consultas|  
|**MT 796**|Respuestas|  
|**MT 798**|Mensaje de propietario|  
|**MT 799**|Mensaje de formato libre|  
  
##  <a name="fsa_intro_qlwo"></a>Categoría 8: Viajeros Cheques  
 En la tabla siguiente describe los mensajes de la categoría 8: los Cheques.  
  
|Tipo de mensaje|Description|  
|------------------|-----------------|  
|**MT 800**|MT ventas de 800 T/C y consejos de liquidación [único]|  
|**MT 801**|MT 801 T/C varios consejos de ventas|  
|**MT 802**|Consejos de liquidación de MT 802 T/C|  
|**MT 810**|Solicitud de reembolso de MT 810 T/C|  
|**MT 812**|Autorización de reembolso de MT 812 T/C|  
|**MT 813**|Confirmación de reembolso de MT 813 T/C|  
|**MT 820**|Solicitar MT 820 de acciones de T/C|  
|**MT 821**|Adición de inventario de MT 821 T/C|  
|**MT 822**|Confirmación de recepción de confianza 822 MT|  
|**MT 823**|Transferencia de inventario de MT 823 T/C|  
|**MT 824**|Aviso de cancelación/destrucción de MT 824 T/C inventario|  
|**MT 890**|MT 890 consejos de cargos, interés y otros ajustes|  
|**MT 891**|MT 891 solicitud de pago de cargos, interés y otros gastos|  
|**MT 892**|MT 892 solicitud de cancelación|  
|**MT 895**|Las consultas MT 895|  
|**MT 896**|Responde a MT 896|  
|**MT 898**|MT 898 mensaje propietario|  
|**MT 899**|Mensaje de formato libre 899 MT|  
  
##  <a name="fsa_intro_sptj"></a>Categoría 9: Estado de cliente y la gestión de efectivo  
 En la tabla siguiente describe los mensajes de la categoría 9: administración de efectivo y el estado de cliente.  
  
|Tipo de mensaje|Description|  
|------------------|-----------------|  
|**MT 900**|Confirmación de débito|  
|**MT 910**|Confirmación de crédito|  
|**MT 920**|Mensaje de solicitud|  
|**MT 935**|Consejos de cambio de velocidad|  
|**MT 940**|Mensaje de la instrucción de cliente|  
|**MT 941**|Informes de saldo|  
|**MT 942**|Informe de las transacciones provisional|  
|**MT 950**|Mensaje de instrucción|  
|**MT 960**|Solicitud de mensaje de inicio del servicio|  
|**MT 961**|Mensaje de respuesta de inicio|  
|**MT 962**|Mensaje de la clave del servicio|  
|**MT 963**|Mensaje de confirmación de clave|  
|**MT 964**|Mensaje de error|  
|**MT 965**|Error de mensaje de servicio de clave|  
|**MT 966**|Interrumpa el mensaje del servicio|  
|**MT 967**|Mensaje de confirmación de interrupción|  
|**MT 970**|Instrucción de compensación|  
|**MT 971**|Informes de saldo de compensación|  
|**MT 972**|Estado provisional de compensación|  
|**MT 973**|Mensaje de solicitud de compensación|  
|**MT 985**|Consulta de estado|  
|**MT 986**|Informe de estado|  
|**MT 990**|Consejos de cargos, interés y otros ajustes|  
|**MT 991**|Solicitud de pago de cargos, interés y otros gastos|  
|**MT 992**|Solicitud de cancelación|  
|**MT 995**|Consultas|  
|**MT 996**|Respuestas|  
|**MT 998**|Mensaje de propietario|  
|**MT 999**|Mensaje de formato libre|  
  
 Todos los mensajes siguen la *SWIFT estándares versión guía 2008* especificaciones. Para obtener más información sobre la *Guía de la versión de SWIFT estándares*, vea el sitio Web de SWIFT en [http://go.microsoft.com/fwlink/?LinkId=27885](http://go.microsoft.com/fwlink/?LinkId=27885).  
  
## <a name="see-also"></a>Vea también  
 [Mensajes de SWIFT](../../adapters-and-accelerators/accelerator-swift/swift-messages.md)