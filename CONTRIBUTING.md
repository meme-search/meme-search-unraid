# Contributing

The repository is in its design and incubation stage. Before implementing an
image or Community Applications template, open an issue describing the proposed
network, storage, upgrade, and support contract.

Pull requests must:

- consume versioned upstream Meme Search releases rather than fork application
  source;
- keep PostgreSQL and the Python service private;
- preserve explicit, persistent data boundaries;
- include tests for the behavior they introduce; and
- avoid describing the integration as officially supported while the warning in
  the README remains in force.

