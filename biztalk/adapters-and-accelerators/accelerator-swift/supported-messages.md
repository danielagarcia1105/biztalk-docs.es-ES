---
title: Admite mensajes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SWIFT messages, supported message types
ms.assetid: 9e059f86-05b1-4c6b-afa8-0ca969874a97
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6caa757624a33eaa514c56c9ea7324ff9a0cfb71
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998853"
---
# <a name="supported-messages"></a>Mensajes admitidos
Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] proporciona una lista de mensajes de Microsoft y SWIFT. Los mensajes se dividen en varias categorías financieras que se enumeran a continuación.  
  
 Esta sección contiene:  
  
-   [Mensajes de SWIFT - Microsoft](#fsa_intro_xtkj)  
  
-   [Categoría 0: Los mensajes del sistema FIN](#fsa_intro_xcpk)  
  
-   [Categoría 1: Los pagos del cliente y comprobaciones](#fsa_intro_lxnf)  
  
-   [Categoría 2: Las transferencias de institución financiera](#fsa_intro_fywg)  
  
-   [Categoría 3: Treasury mercados Exchange externa, mercados de dinero y derivados](#fsa_intro_qipa)  
  
-   [Categoría 4: Colecciones y letras efectivo](#fsa_intro_ruuc)  
  
-   [Categoría 5: Los mercados de valores](#fsa_intro_iitn)  
  
-   [Categoría de 6: Treasury mercados metales preciosos](#fsa_intro_bjez)  
  
-   [Categoría 7: Documentales créditos y garantías](#fsa_intro_vhkw)  
  
-   [Categoría de 8: Los viajeros Cheques](#fsa_intro_qlwo)  
  
-   [Categoría 9: Estado de cliente y la gestión de efectivo](#fsa_intro_sptj)  
  
##  <a name="fsa_intro_xtkj"></a> Mensajes de SWIFT - Microsoft  
 En la tabla siguiente describe los mensajes de SWIFT Microsoft para los tipos de servicio GPA y Control de FIN.  
  
|Tipo de mensaje|Descripción|  
|------------------|-----------------|  
|**02**|Mensaje de solicitud de inicio de sesión|  
|**03**|Seleccione el comando|  
|**05**|Comando Quit|  
|**06**|Comando de cierre de sesión|  
|**12**|Solicitud de Asia Pacífico quitar del sistema|  
|**13**|Confirmación de Asia Pacífico de anulación del sistema|  
|**14**|Solicitud del sistema para quitar LT|  
|**15**|Confirmación de anulación LT iniciadas por el usuario del sistema|  
|**21**|Confirmación de un mensaje de GPA enviado por un LT (ACK/NAK)|  
|**21**|Confirmación de un mensaje de GPA recibido por un LT (ACK/NAK)|  
|**21**|Confirmación de un mensaje FIN enviado por un LT (ACK/NAK)|  
|**21**|Confirmación de un mensaje FIN recibido por un LT (UAK/UNK)|  
|**22**|Confirmación de inicio de sesión positivo (LAK)|  
|**23**|Confirmación de una solicitud de Select (SAK)|  
|**25**|Salga de confirmación|  
|**26**|Confirmación de cierre de sesión|  
|**33**|Solicitud de Asia Pacífico de anulación de usuario|  
|**35**|Solicitud de usuario para anular LT (anulación LT)|  
|**42**|Confirmación de inicio de sesión (LNK)|  
|**43**|Seleccione una confirmación negativa (SNK)|  
  
##  <a name="fsa_intro_xcpk"></a> Categoría 0: Los mensajes del sistema FIN  
 En la tabla siguiente describe la forma de mensajes categoría 0: financieros mensajes del sistema, incluido el usuario para SWIFT y SWIFT para el usuario.  
  
|Tipo de mensaje|Descripción|  
|------------------|-----------------|  
|**008 MT**|Solicitud del sistema para salir|  
|**009 MT**|Solicitud de sistema para el cierre de sesión|  
|**010 MT**|Advertencia de no entrega|  
|**011 MT**|Notificación de entrega|  
|**012 MT**|Notificación de remitente|  
|**015 MT**|NAK retrasada|  
|**019 MT**|Anular la notificación|  
|**020 MT**|Solicitud de recuperación (texto e historial)|  
|**021 MT**|Mensaje recuperado (texto e historial)|  
|**022 MT**|Solicitud de recuperación (historial)|  
|**023 MT**|Mensaje recuperado (historial)|  
|**028 MT**|Solicitud de estado de mensaje FIN copia|  
|**029 MT**|Informe de estado de mensaje FIN copia|  
|**031 MT**|Solicitud de historial de sesión|  
|**MT 032**|Solicitud de estado de entrega subconjunto|  
|**MT 035**|Solicitud de instrucciones de entrega|  
|**MT 036**|Solicitud de historial LT|  
|**MT 037**|Solicitud de estado de zona horaria|  
|**MT 041**|Seleccione la solicitud de estado de FIN|  
|**MT 042**|Corte tiempos de solicitud de lista|  
|**MT 043**|Solicitud de lista de días no laborables|  
|**MT 044**|Nueva definición de informe sin entregar reglas|  
|**MT 045**|Solicitud de cambio de tiempo de comprobación diaria|  
|**MT 046**|Solicitud de informe de mensaje no entregado|  
|**MT 047**|¡¡¡Redefinición solicitud de entrega instrucciones|  
|**MT 048**|Solicitud de informe no entregados de reglas|  
|**MT 049**|Consulta en tiempo de comprobación de informe diario|  
|**MT 051**|Informe de historial de sesión|  
|**MT 052**|Informe de estado de entrega subconjunto|  
|**MT 055**|Informe de instrucciones de entrega|  
|**MT 056**|Informe de historial de LT|  
|**MT 057**|Informe de estado de zona horaria|  
|**MT 061**|Seleccione el informe de estado de FIN|  
|**MT 062**|Informe de lista de la hora de finalización|  
|**MT 063**|Informe de lista de días no laborables|  
|**MT 064**|Informe de cambio de reglas sin entregar informes|  
|**MT 065**|Informe de cambios de tiempo para el informe de comprobación de diario|  
|**MT 066**|Solicitado el informe de mensaje no entregado|  
|**MT 067**|Informe de redefinición de instrucciones de entrega|  
|**MT 068**|Reglas de informe no entregado|  
|**MT 069**|Estado de tiempo de informe de comprobación diaria|  
|**MT 072**|Selección del modo de prueba|  
|**MT 073**|Ejemplo de mensaje de solicitud|  
|**MT 074**|Solicitud de difusión|  
|**MT 075**|Solicitudes de certificación|  
|**MT 076**|Error de certificación|  
|**MT 077**|Criterios adicionales de FIN|  
|**MT 081**|Informe de comprobación de diario|  
|**MT 082**|Informe de mensaje no entregado a una hora fija|  
|**MT 083**|Informe de mensaje no entregado en la hora de finalización|  
|**MT 085**|Información de entrega de ICC|  
|**MT 087**|Respuesta de certificación|  
|**MT 090**|Mensaje de usuario para SWIFT|  
|**092 MT**|Mensaje de SWIFT para el usuario|  
|**094 MT**|Broadcast|  
|**096 MT**|Copia FIN al mensaje de la entidad Central|  
|**097 MT**|Notificación de autorización o rechazo de mensaje FIN copia|  
  
##  <a name="fsa_intro_lxnf"></a> Categoría 1: Los pagos del cliente y comprobaciones  
 En la tabla siguiente se describe los mensajes de categoría 1: los pagos y comprobaciones.  
  
|Tipo de mensaje|Descripción|  
|------------------|-----------------|  
|**MT 101**|Solicitud de transferencia|  
|**102 MT**|Transferencia de cliente múltiples|  
|**MT 102 +**|Transferencia de varios clientes (STP)|  
|**MT 103**|Transferencia de crédito solo cliente|  
|**MT 103 +**|Transferencia de crédito solo cliente (STP)|  
|**MT 104**|Mensaje de transferencia de adeudo directo y solicitud de débito|  
|**MT 105**|Sobre EDIFACT|  
|**106 MT**|Sobre EDIFACT|  
|**MT 107**|Mensaje general Direct débito|  
|**MT 110**|Consejo de cheques|  
|**MT 111**|Solicitud para detener el pago de un Cheque|  
|**MT 112**|Estado de una solicitud para detener el pago de un Cheque|  
|**MT 121**|Transferencia de fondos entre bancos más múltiples (FINPAY EDIFACT)|  
|**190 MT**|Consejos de cargos, intereses y otros ajustes|  
|**MT 191**|Solicitud de pago de cargos, intereses y otros gastos|  
|**192 MT**|Solicitud de cancelación|  
|**MT 195**|Consultas|  
|**MT 196**|Respuestas|  
|**198 MT**|Mensajes en propiedad|  
|**MT 199**|Mensaje de formato libre|  
  
##  <a name="fsa_intro_fywg"></a> Categoría 2: Las transferencias de institución financiera  
 En la tabla siguiente se describe los mensajes de la categoría 2: las transferencias de tu institución financiera.  
  
|Tipo de mensaje|Descripción|  
|------------------|-----------------|  
|**MT 200**|Transferencia de la institución financiera por cuenta propia|  
|**MT 201**|Transferencia de múltiples institución financiera por cuenta propia|  
|**MT 202**|Transferencia de la institución financiera general|  
|**203 MT**|Transferencia de múltiples institución financiera General|  
|**204 MT**|Mensaje de mercados financieros adeudo directo|  
|**MT 205**|Ejecución de la transferencia de institución financiera|  
|**MT 206**|Mensaje de truncamiento cheque|  
|**207 MT**|Solicitud de transferencia de la institución financiera|  
|**210 MT**|Aviso de recepción|  
|**MT 256**|Consejo de impago de Cheques|  
|**MT 290**|Consejos de cargos, intereses y otros ajustes|  
|**MT 291**|Solicitud de pago de cargos, intereses y otros gastos|  
|**MT 292**|Solicitud de cancelación|  
|**MT 293**|Mensaje de información de servicio|  
|**MT 295**|Consultas|  
|**MT 296**|Respuestas|  
|**MT 298**|Mensajes en propiedad|  
|**MT 299**|Mensaje de formato libre|  
  
##  <a name="fsa_intro_qipa"></a> Categoría 3: Treasury mercados Exchange externa, mercados de dinero y derivados  
 En la tabla siguiente se describe los mensajes de la categoría 3: Treasury mercados extranjera, mercados de dinero y derivados.  
  
|Tipo de mensaje|Descripción|  
|------------------|-----------------|  
|**300 MT**|Confirmación de cambio de divisa extranjera|  
|**MT 303**|Instrucción de asignación de opción Forex/moneda|  
|**304 MT**|Consejo o instrucción de una oferta de terceros|  
|**305 MT**|Confirmación de la opción de divisa extranjera|  
|**MT 306**|Confirmación de la opción de divisa extranjera|  
|**MT 307**|Consejo o instrucción de una oferta de terceros FX|  
|**MT 308**|Instrucciones para la liquidación Gross/Net de ofertas de terceros FX|  
|**320 MT**|Confirmación de préstamo/ingreso fijo|  
|**MT 321**|Instrucciones para liquidar un préstamo/ingreso de terceros|  
|**330 MT**|Llamadas/aviso de confirmación de ingresos/préstamo|  
|**MT 340**|Confirmación del acuerdo de tasa de avance|  
|**MT 341**|Confirmación de liquidación del acuerdo de tasa de avance|  
|**350 MT**|Consejo de pago de intereses de ingresos/préstamo|  
|**MT 360**|Confirmación derivados de moneda única de interés|  
|**MT 361**|Entre la confirmación de intercambio de tasa de interés de moneda|  
|**MT 362**|Restablecimiento de tasa de interés o aviso de pago|  
|**364 MT**|Confirmación de terminación/Recouponing intercambio de moneda única tasa de interés|  
|**MT 365**|Entre la confirmación de terminación/Recouponing intercambio de moneda tasa de interés|  
|**MT 380**|Orden de cambio de divisa extranjera|  
|**MT 381**|Confirmación de pedido de cambio de divisa extranjera|  
|**390 MT**|Consejos de cargos, intereses y otros ajustes|  
|**MT 391**|Solicitud de pago de cargos, intereses y otros gastos|  
|**MT 392**|Solicitud de cancelación|  
|**395 MT**|Consultas|  
|**MT 396**|Respuestas|  
|**MT 398**|Mensajes en propiedad|  
|**MT 399**|Mensaje de formato libre|  
  
##  <a name="fsa_intro_ruuc"></a> Categoría 4: Colecciones y letras efectivo  
 En la tabla siguiente se describe los mensajes de la categoría 4: las colecciones y las letras de efectivo.  
  
|Tipo de mensaje|Descripción|  
|------------------|-----------------|  
|**MT 400**|Consejos de pago|  
|**405 MT**|Limpiar la colección|  
|**MT 410**|Acknowledgement|  
|**412 MT**|Consejos de aceptación|  
|**MT 416**|Consejo de que no son de pago no de aceptación|  
|**420 MT**|Tracer|  
|**MT 422**|Consejos de alcance y solicitud de instrucciones|  
|**MT 430**|Modificación de instrucciones|  
|**450 MT**|Consejos de crédito letra efectivo|  
|**MT 455**|Aviso de ajuste de crédito de letra efectivo|  
|**MT 456**|Consejos de Dishonour|  
|**490 MT**|Consejos de cargos, intereses y otros ajustes|  
|**MT 491**|Solicitud de pago de cargos, intereses y otros gastos|  
|**MT 492**|Solicitud de cancelación|  
|**495 MT**|Consultas|  
|**MT 496**|Respuestas|  
|**MT 498**|Mensajes en propiedad|  
|**499 MT**|Mensaje de formato libre|  
  
##  <a name="fsa_intro_iitn"></a> Categoría 5: Los mercados de valores  
 En la tabla siguiente se describe los mensajes de la categoría 5: los mercados de valores.  
  
|Tipo de mensaje|Descripción|  
|------------------|-----------------|  
|**MT 500**|Instrucciones para el registro|  
|**501 MT**|Confirmación de registro o de modificación|  
|**MT 502**|Pedido de comprar o vender|  
|**MT 503**|Notificación colateral|  
|**MT 504**|Propuesta colateral|  
|**MT 505**|Sustitución colateral|  
|**506 MT**|Declaración de exposición y garantías|  
|**507 MT**|Estado colateral y consejos de procesamiento|  
|**MT 508**|Posición dentro de un aviso|  
|**MT 509**|Mensaje de estado de intercambios|  
|**MT 510**|Estado de registro y consejos de procesamiento|  
|**MT 513**|Consejos de cliente de ejecución|  
|**MT 514**|Instrucción de asignación de comercio|  
|**MT 515**|Cliente de confirmación de compra o venta|  
|**MT 516**|Confirmación de préstamo de valores|  
|**MT 517**|Afirmación de confirmación de comercio|  
|**MT 518**|Confirmación de comercio del lado del mercado de valores|  
|**MT 519**|Modificación de detalles de cliente|  
|**MT 524**|Instrucción intra-posición|  
|**MT 526**|Valores generales de préstamos mensaje/pedir prestados|  
|**MT 527**|Instrucción colateral Tri de terceros|  
|**MT 528**|Instrucción etc. liquidación del lado cliente|  
|**MT 529**|Instrucción de liquidación de mercado lado etc.|  
|**MT 530**|Comando de procesamiento de transacciones|  
|**MT 535**|Instrucción de participación|  
|**MT 536**|Instrucción de transacciones|  
|**MT 537**|Instrucción de las transacciones pendientes|  
|**MT 538**|Instrucción de avisos de posición dentro de un|  
|**540 MT**|Recibir de forma gratuita|  
|**MT 541**|Recibir pagos|  
|**MT 542**|Entregar de forma gratuita|  
|**MT 543**|Entregar contra el pago|  
|**MT 544**|Recibir confirmación gratis|  
|**545 MT**|Recibir confirmación de pago|  
|**546 MT**|Entregar confirmación gratis|  
|**MT 547**|Cumplir con la confirmación de pago|  
|**MT 548**|Estado de liquidación y consejos de procesamiento|  
|**MT 549**|Solicitud para obtener consejos/Procesamiento de una instrucción|  
|**558 MT**|Estado colateral Tri de terceros y consejos de procesamiento|  
|**MT 559**|Notificación de los agentes de versiones de pago|  
|**MT 564**|Notificación de acción corporativa|  
|**MT 565**|Instrucción de acción corporativa|  
|**MT 566**|Confirmación de acción corporativa|  
|**MT 567**|Estado de la acción corporativa y consejos de procesamiento|  
|**MT 568**|Acción corporativa narrativa|  
|**MT 569**|Tri de terceros colaterales y la declaración de exposición|  
|**MT 574**|(IRSLST) ANR IRS 1441|  
|**MT 574**|(W8BENO) ANR IRS 1441|  
|**MT 575**|Informe de actividad combinada|  
|**MT 576**|Instrucción de pedidos pendientes|  
|**MT 577**|Instrucción de números|  
|**MT 578**|Liquidación Allegement|  
|**MT 579**|Números de certificado|  
|**MT 581**|Mensaje de ajuste colateral|  
|**MT 582**|Aviso o notificación de reembolso|  
|**MT 584**|Instrucción de etc. pendientes en varios temas|  
|**MT 586**|Instrucción de liquidación Allegements|  
|**MT 587**|Instrucción de recepción depositario|  
|**588 MT**|Confirmación de recepción depositario|  
|**MT 589**|Estado de recepción depositario y consejos de procesamiento|  
|**MT 590**|Consejos de cargos, intereses y otros ajustes|  
|**MT 591**|Solicitud de pago de cargos, intereses y otros gastos|  
|**MT 592**|Mensaje de SWIFT para el usuario|  
|**MT 595**|Preguntas|  
|**MT 596**|Respuestas|  
|**MT 598**|Mensajes en propiedad|  
|**MT 599**|Mensaje de formato libre|  
  
##  <a name="fsa_intro_bjez"></a> Categoría de 6: Treasury mercados metales preciosos  
 En la tabla siguiente se describe los mensajes de categoría 6: metales preciosos de tesorería mercados, las sindicaciones de mercados Tesoro y mensajes comunes de tesorería mercados.  
  
|Tipo de mensaje|Descripción|  
|------------------|-----------------|  
||**Tesorería mercados metales preciosos**|  
|**600 MT**|Confirmación de metal comerciales|  
|**MT 601**|Confirmación de la opción de metales preciosos|  
|**604 MT**|Orden de transferencia y entrega de metales preciosos|  
|**MT 605**|Aviso de metales preciosos para recibir|  
|**MT 606**|Consejos de metales preciosos débito|  
|**MT 607**|Consejos de metales preciosos crédito|  
|**MT 608**|Instrucción de una cuenta de Metal|  
|**MT 609**|Instrucción de contratos de Metal|  
|**MT 620**|Confirmación de metal préstamo fijo/ingreso|  
||**Las sindicaciones de mercados de tesorería**|  
|**MT 643**|Aviso de reducción/renovación|  
|**MT 644**|Consejos de velocidad y la corrección de cantidad|  
|**MT 645**|Aviso de cuota de vencimiento|  
|**MT 646**|Pago de entidad de seguridad o de interés|  
|**MT 649**|Mensaje de instalación sindicado general|  
||**Mercados de tesorería - mensajes comunes**|  
|**MT 690**|Consejos de cargos, intereses y otros ajustes|  
|**MT 691**|Solicitud de pago de cargos, intereses y otros gastos|  
|**MT 692**|Solicitud de cancelación|  
|**MT 695**|Consultas|  
|**MT 696**|Respuestas|  
|**MT 698**|Mensajes en propiedad|  
|**MT 699**|Mensaje de formato libre|  
  
##  <a name="fsa_intro_vhkw"></a> Categoría 7: Documentales créditos y garantías  
 En la tabla siguiente se describe los mensajes de la categoría de 7: documental créditos y garantías.  
  
|Tipo de mensaje|Descripción|  
|------------------|-----------------|  
|**700 MT**|Problema de un crédito documental|  
|**MT 701**|Problema de un crédito documental|  
|**MT 705**|Consejos previa de un crédito documental|  
|**MT 707**|Modificación de un crédito documental|  
|**MT 710**|Consejo de un crédito de los bancos documental tercer|  
|**MT 711**|Consejo de un crédito de los bancos documental tercer|  
|**MT 720**|Transferencia de un crédito documental|  
|**MT 721**|Transferencia de un crédito documental|  
|**MT 730**|Acknowledgement|  
|**MT 732**|Consejos de descarga|  
|**MT 734**|Consejo de denegación|  
|**MT 740**|Autorización a reembolsar|  
|**MT 742**|Notificación de reembolso|  
|**MT 747**|Modificación de una autorización para pagar|  
|**750 MT**|Consejo de discrepancia|  
|**MT 752**|Autorización a pagar, acepte o negociar|  
|**MT 754**|Consejos de aceptación/pago/negociación|  
|**MT 756**|Consejo de reembolso o de pago|  
|**MT 760**|Garantía de|  
|**MT 767**|Modificación de la garantía|  
|**MT 768**|Confirmación de un mensaje de garantía|  
|**MT 769**|Consejos de reducción o versión|  
|**MT 790**|Consejos de cargos, intereses y otros ajustes|  
|**MT 791**|Solicitud de pago de cargos, intereses y otros gastos|  
|**MT 792**|Solicitud de cancelación|  
|**MT 795**|Consultas|  
|**MT 796**|Respuestas|  
|**MT 798**|Mensajes en propiedad|  
|**799 MT**|Mensaje de formato libre|  
  
##  <a name="fsa_intro_qlwo"></a> Categoría de 8: Los viajeros Cheques  
 En la tabla siguiente se describe los mensajes de categoría 8: los viajeros Cheques.  
  
|Tipo de mensaje|Descripción|  
|------------------|-----------------|  
|**800 MT**|MT ventas de T/C 800 y consejos de liquidación [simple]|  
|**MT 801**|Múltiplo de T/C 801 MT ventas consejos|  
|**MT 802**|Consejos de liquidación de T/C 802 MT|  
|**MT 810**|Solicitud de reembolso de T/C 810 MT|  
|**MT 812**|Autorización de reembolso de T/C 812 MT|  
|**MT 813**|Confirmación de reembolso de T/C 813 MT|  
|**MT 820**|MT 820 solicitar material de T/C|  
|**MT 821**|Adición de inventario de T/C 821 MT|  
|**MT 822**|Confirmación de recibo de confianza 822 MT|  
|**MT 823**|Transferencia de inventario de T/C 823 MT|  
|**MT 824**|Aviso de destrucción/cancelación de inventario de MT 824 T/C|  
|**MT 890**|MT 890 consejos de cargos, intereses y otros ajustes|  
|**MT 891**|MT 891 de solicitud de pago de cargos, intereses y otros gastos|  
|**MT 892**|MT 892 de solicitud de cancelación|  
|**MT 895**|Consulta de MT 895|  
|**MT 896**|Responde MT 896|  
|**MT 898**|MT 898 mensajes en propiedad|  
|**899 MT**|Mensaje de formato libre 899 MT|  
  
##  <a name="fsa_intro_sptj"></a> Categoría 9: Estado de cliente y la gestión de efectivo  
 En la tabla siguiente se describe los mensajes de categoría de 9: administración de efectivo y el estado de cliente.  
  
|Tipo de mensaje|Descripción|  
|------------------|-----------------|  
|**900 MT**|Confirmación de débito|  
|**MT 910**|Confirmación de crédito|  
|**920 MT**|Mensaje de solicitud|  
|**MT 935**|Consejos de cambio de velocidad|  
|**MT 940**|Mensaje al cliente de instrucción|  
|**941 MT**|Informes de saldo|  
|**942 MT**|Informe de las transacciones provisionales|  
|**MT 950**|Mensaje de la instrucción|  
|**960 MT**|Solicitud de mensaje de inicio del servicio|  
|**MT 961**|Mensaje de respuesta de iniciación|  
|**MT 962**|Mensaje de la clave de servicio|  
|**MT 963**|Mensaje de confirmación de clave|  
|**MT 964**|Mensaje de error|  
|**MT 965**|Error en el mensaje de la clave de servicio|  
|**MT 966**|Suspender mensaje de servicio|  
|**MT 967**|Mensaje de confirmación de suspensión|  
|**MT 970**|Instrucción de compensación|  
|**MT 971**|Informes de saldo de compensación|  
|**MT 972**|Estado provisional de compensación|  
|**MT 973**|Mensaje de solicitud de compensación|  
|**MT 985**|Consulta de estado|  
|**MT 986**|Informe de estado|  
|**990 MT**|Consejos de cargos, intereses y otros ajustes|  
|**MT 991**|Solicitud de pago de cargos, intereses y otros gastos|  
|**992 MT**|Solicitud de cancelación|  
|**995 MT**|Consultas|  
|**MT 996**|Respuestas|  
|**998 MT**|Mensajes en propiedad|  
|**MT 999**|Mensaje de formato libre|  
  
 Todos los mensajes siguen la *SWIFT estándares versión guía 2008* especificaciones. Para obtener más información sobre la *Guía de la versión SWIFT estándares*, vea el sitio Web de SWIFT en [ http://go.microsoft.com/fwlink/?LinkId=27885 ](http://go.microsoft.com/fwlink/?LinkId=27885).  
  
## <a name="see-also"></a>Vea también  
 [Mensajes de SWIFT](../../adapters-and-accelerators/accelerator-swift/swift-messages.md)