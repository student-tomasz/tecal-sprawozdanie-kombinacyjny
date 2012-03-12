$lc = "xelatex"
$lf = "-interaction=nonstopmode"

$exec = "sprawozdanie-2.pdf"

rule '.pdf' => '.tex' do |t|
  2.times do
    sh "#{$lc} #{$lf} #{t.source}"
  end
end

task :default => :build

task :build => $exec do
end

task :show => $exec do
  sh "open #{$exec}" rescue nil
end

task :clean do
  %w{*.out *.log *.aux *.pdf}.each do |f|
    sh "rm #{f}" rescue nil
  end
end
