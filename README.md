# INSTRUMENTAÇÃO

Sistema de Gestão de Instrumentação e Calibração.

## Objetivo
Centralizar o cadastro, planejamento, execução e histórico de calibrações, padrões, certificados, manutenção, não conformidades, documentos, indicadores e alertas.

## Arquitetura funcional
- Dashboard
- Instrumentos
- Calibração
- Padrões de referência
- Certificados
- Manutenção
- Não conformidades
- Movimentações
- Setores
- Tipos de instrumentos
- Critérios metrológicos
- Alertas
- Indicadores/KPIs
- Relatórios
- Histórico
- Documentos
- Usuários e permissões
- Inteligência/IA
- Configurações

## Princípio central
Cada instrumento possui um cadastro único e se relaciona com calibrações, resultados, certificados, padrões, manutenções, NCs, movimentações e histórico.

## Diretriz de UI
Interface web responsiva, profissional e industrial, inspirada em produtos modernos como Linear, com navegação lateral, cards de indicadores, tabelas avançadas, filtros, busca global, status visuais e tema escuro como opção. Identidade visual Astra Foods: vermelho, branco, preto e tons neutros.

## Stack sugerida
React + TypeScript + Vite + Tailwind CSS + shadcn/ui + PostgreSQL/Supabase.

## Próxima etapa
O frontend e backend devem ser construídos modularmente, com dados relacionais e regras de negócio centralizadas. O projeto deve ser preparado para integração com Lovable.
