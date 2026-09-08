# INSTRUÇÃO DE RECONSTRUÇÃO — INSTRUMENTAÇÃO

Reconstruir a aplicação INSTRUMENTAÇÃO do zero. Não preservar telas, componentes ou fluxos antigos. Usar este documento como especificação funcional inicial.

## 1. Dashboard
Cards: total de instrumentos, calibrados, a vencer, vencidos, em manutenção, com NC, calibrações do mês e certificados pendentes. Gráficos por situação, setor e tipo. Calendário de vencimentos. Lista de ações pendentes.

## 2. Instrumentos
Cadastro único com código, TAG, patrimônio, número de série, tipo, fabricante, modelo, capacidade, unidade, setor, área, equipamento/localização, periodicidade, última calibração, próxima calibração, critério de aceitação, responsável, status e documentos/fotos. Criar páginas para ativos, bloqueados e movimentações.

## 3. Calibração
Planejamento por dia/semana/mês, filtros por setor/tipo/status/responsável e criação de calibração. Registro com instrumento, data/hora, responsável, padrão utilizado, método e condições ambientais. Tabela de pontos de calibração com valor padrão, valor indicado, erro, tolerância e resultado. Calcular automaticamente erro e aprovação/reprovação.

## 4. Padrões de referência
Cadastro de padrões: código, instrumento, fabricante, modelo, série, faixa, resolução, certificado, laboratório, calibração, vencimento, incerteza e rastreabilidade. Impedir/alertar uso de padrão vencido.

## 5. Certificados
Biblioteca vinculada aos instrumentos e padrões. Número, laboratório, data, validade, arquivo PDF e status. Alertar certificado pendente ou vencido.

## 6. Manutenção
Preventiva e corretiva. Registrar instrumento, problema, abertura, responsável, ação, peças, custo opcional, conclusão e status. Manter histórico.

## 7. Não conformidades
Ao reprovar uma calibração, permitir gerar NC vinculada automaticamente. Registrar problema, impacto, bloqueio, investigação, ação corretiva, responsável, prazo, evidências e encerramento.

## 8. Bloqueio
Instrumento reprovado pode ser colocado automaticamente em BLOQUEADO. Exibir claramente que não deve ser utilizado. Permitir retorno após manutenção/recalibração/aprovação.

## 9. Movimentações
Histórico de transferência entre setores/localizações, com origem, destino, data, responsável e motivo.

## 10. Cadastros auxiliares
Setores, tipos de instrumentos, unidades, métodos, periodicidades, critérios de aceitação, status e usuários/perfis.

## 11. Critérios metrológicos
Permitir configurar tolerâncias por tipo/modelo/instrumento, unidade e pontos. Exemplos: termômetro ±0,5 °C; balança conforme critério definido. Nunca codificar tolerâncias arbitrárias sem configuração.

## 12. Alertas
Vencido, vence em 7 dias, 15 dias e 30 dias, certificado pendente, padrão vencido, calibração reprovada, manutenção atrasada e NC próxima do prazo.

## 13. Indicadores
% calibrados no prazo, % reprovados, calibrações realizadas/previstas, atrasos, instrumentos em manutenção, NCs abertas, tempo médio de correção, reincidência e tendência de erro.

## 14. Relatórios
Relatório de calibração, relatório mensal, instrumentos vencidos, padrões, certificados, manutenção, NC e histórico. Exportar PDF/Excel/CSV quando aplicável.

## 15. Histórico
Linha do tempo completa por instrumento: cadastro, calibrações, resultados, certificados, manutenções, NCs, bloqueios, movimentações e alterações relevantes.

## 16. Documentos
Central documental com categorias Certificados, Manuais, Procedimentos, Relatórios, Laudos, Fotos e Ordens de Serviço. Vinculação ao registro correto.

## 17. Usuários e permissões
Administrador, Instrumentação, Qualidade, Gestor e Consulta. Aplicar controle de acesso às operações.

## 18. Busca global
Pesquisar por código, TAG, patrimônio, série, certificado, setor ou tipo e abrir o registro relacionado.

## 19. Etiquetas e QR Code
Gerar etiqueta do instrumento com identificação, data de calibração, próxima calibração, status e QR Code. QR Code deve abrir o cadastro do instrumento.

## 20. Inteligência/IA
Preparar módulo para leitura de certificados/PDFs e extração de campos, leitura de etiquetas por foto, identificação de tendências de erro e alertas analíticos. IA não deve alterar dados críticos sem confirmação do usuário.

## 21. Configurações
Empresa, logo, identidade visual, setores, tipos, periodicidades, tolerâncias, permissões, alertas, unidades, regras de aprovação e integrações.

## Banco de dados inicial
Criar modelo relacional com entidades: instruments, sectors, instrument_types, calibration_standards, calibration_standard_certificates, calibrations, calibration_points, certificates, maintenance_orders, nonconformities, instrument_movements, documents, metrology_criteria, users/profiles, notifications e audit_logs. Usar IDs, timestamps, foreign keys, índices e status controlados.

## Regras críticas
1. Um instrumento possui um cadastro central único.
2. Toda calibração deve apontar para um instrumento.
3. Toda calibração deve registrar o padrão utilizado quando aplicável.
4. Erro = indicação do instrumento - valor de referência.
5. Resultado deve ser comparado ao critério configurado.
6. Reprovação deve permitir bloqueio e NC.
7. Próximo vencimento deve ser calculado pela periodicidade configurada, podendo ser ajustado somente por usuário autorizado.
8. Alterações críticas devem entrar em audit_logs.
9. Nunca apagar histórico metrológico; usar inativação/arquivamento quando necessário.
10. Dashboard deve refletir dados reais do banco, não números mockados em produção.

## Design
Nome do produto: INSTRUMENTAÇÃO. Visual moderno, limpo, industrial e sofisticado. Sidebar fixa, busca global, breadcrumbs, tabelas com filtros, drawers/modais para edição, cards e gráficos. Tema escuro e claro. Preferência por dark mode profissional inspirado em Linear, com roxo/azul para elementos de interface e vermelho apenas para identidade Astra Foods e situações críticas. Responsivo para desktop e tablet.

## Navegação
Dashboard / Instrumentos / Calibração / Padrões / Certificados / Manutenção / Não Conformidades / Movimentações / Indicadores / Relatórios / Documentos / Alertas / Inteligência / Configurações.

## Critério de entrega
A primeira versão deve funcionar de ponta a ponta com autenticação, banco, CRUD dos principais cadastros, dashboard real, fluxo de calibração, cálculo de resultados, status, vencimentos e histórico. Depois evoluir para certificados, manutenção, NC, documentos, relatórios e IA.
