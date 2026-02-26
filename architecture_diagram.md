# Autonomous Self-Evolving Trading System Architecture

## Core Components
1. **Master Agent**: Orchestrates all agents, manages strategy lifecycle
2. **Research Agent**: Discovers/validates market signals and strategies
3. **Execution Agent**: Executes trades via CCXT across multiple exchanges
4. **Risk Agent**: Monitors exposure, enforces limits, implements circuit breakers
5. **Optimization Agent**: Continuously tunes strategy parameters via Bayesian optimization
6. **Firestore Database**: Persistent state, strategy registry, market data cache
7. **Telegram Alert System**: Critical notifications for human oversight

## Data Flow
Market Data → Research Agent → Strategy Generation → Master Agent → 
Execution Agent (with Risk Checks) → Performance Data → Optimization Agent → 
Strategy Refinement → Repeat

## Failure Resilience
- Graceful degradation when individual agents fail
- Automatic fallback to conservative strategies during high volatility
- State persistence across system restarts
- Circuit breakers for drawdown protection