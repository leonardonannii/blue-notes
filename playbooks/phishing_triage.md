# Playbook — Phishing (Triage iniziale)

**Scopo:** verifiche di base su email sospette senza aprire link/allegati.

1) **Segnali rapidi:** mittente/dominio simile, urgenza, errori, allegati inattesi.
2) **Verifiche:**
   - Header completo (Return-Path, SPF/DKIM/DMARC se visibili)
   - Passa gli URL in un expander/sandbox (senza cliccarli)
   - Se allegato in quarantena → calcola hash
3) **Azioni immediate:** non aprire link/allegati; avvisa IT; isola il PC se è stato cliccato.
4) **Evidenze da raccogliere:** file .eml, header, orario, utente, URL/IP.
5) **Escalation:** se credenziali inserite → reset forzato + invalidazione sessioni; apri ticket “Account compromise”.
