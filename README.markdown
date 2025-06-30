# Quantum Decoherence Simulation

This project simulates the decoherence of a single qubit under amplitude damping using the QuTiP (Quantum Toolbox in Python) library. The simulation models the evolution of a qubit in a superposition state, tracks its coherence, and computes the expectation values of Pauli operators over time, comparing them with analytical solutions.

## Features
- Simulates a qubit in a superposition state undergoing amplitude damping.
- Uses QuTiP's `mesolve` to solve the Lindblad master equation.
- Computes coherence and expectation values of Pauli operators (`σx`, `σy`, `σz`).
- Plots simulated results alongside analytical solutions for validation.
- Includes error checking to ensure states are stored during simulation.

## Prerequisites
To run the code, you need the following Python packages:
- `numpy`
- `matplotlib`
- `qutip`

Install them using pip:
```bash
pip install numpy matplotlib qutip
```

## Code Description
The script performs the following steps:
1. **Initialization**: Sets up a qubit in a superposition state (`|+> = (|0> + |1>)/sqrt(2)`) using the Hadamard gate equivalent.
2. **Simulation Parameters**:
   - Hilbert space dimension: `N = 2`
   - Time points: `tlist = np.linspace(0, 10, 100)`
   - Amplitude damping rate: `gamma = 0.1`
3. **Operators**:
   - Defines Pauli operators (`σx`, `σy`, `σz`) and collapse operator for amplitude damping.
   - Uses a trivial Hamiltonian (`H = 0`) to focus on decoherence effects.
4. **Simulation**: Solves the Lindblad master equation using `mesolve` with options to store states.
5. **Analysis**:
   - Computes coherence (`|ρ_{01}|`) and expectation values of Pauli operators manually.
   - Compares with analytical solutions for validation.
6. **Visualization**: Plots coherence and expectation values with analytical curves for comparison.

## Usage
1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd <repository-directory>
   ```
2. Ensure dependencies are installed (see Prerequisites).
3. Run the script:
   ```bash
   python quantum_decoherence.py
   ```
4. The script will:
   - Print the initial and final density matrices.
   - Print manual expectation values for `<σx>` and `<σz>` at `t=10`.
   - Display plots comparing simulated and analytical results.

## Output
The script generates two plots:
1. **Coherence Plot**: Shows the decay of coherence (`|ρ_{01}|`) over time, compared with the analytical solution.
2. **Expectation Values Plot**: Displays the expectation values of `σx`, `σy`, and `σz`, alongside their analytical solutions.
- **Coherence Evolution**: ![Coherence Evolution Chart](/amplitude_damping.png/qubit_noise_simulation_results.png)


## Notes
- The script assumes familiarity with quantum mechanics and QuTiP.
- The simulation uses a trivial Hamiltonian to isolate the effects of amplitude damping.
- Ensure your QuTiP version supports the `store_states` option in `mesolve`. If states are not stored, a `ValueError` will be raised.

## License
This project is licensed under the MIT License.
